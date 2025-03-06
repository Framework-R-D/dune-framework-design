Functional programming
----------------------

Phlex supports a *functional programming* paradigm, where data-processing occurs by favoring the use of *functions* instead of the direct manipulation of stateful objects.
The processing of data happens by using chained operations, where the output of one function serves as the input to other functions.

For example, given two functions:

.. math::
   f: \mbox{Wires} \rightarrow \mbox{Hits}

   g: \mbox{Hits} \rightarrow \mbox{Tracks}

a composite function :math:`h: \mbox{Wires} \rightarrow \mbox{Tracks}` can be constructed such that:

.. math::
   ts = h(ws) = g(f(ws)) = (f \circ g)(ws)

or :math:`h = f \circ g`, where :math:`ws \in \mbox{Wires}` and :math:`ts \in \mbox{Tracks}`.

In reality, the creation of tracks from wire signals is much more complicated [#f1]_.
However, as seen above, functional programming permits a mathematical description of the data-processing to be performed.
Expressing the processing needs according to mathematics enables:

- the use of mathematical rules to optimize the processing of the data,
- naturally reproducible results, assuming the functions are :ref:`pure <pure-functions>`,
- parallel invocations of pure functions with no possibility of data races.

.. _pure-functions:

Pure functions
^^^^^^^^^^^^^^

According to Wikipedia [Wiki-pure]_, a pure function has the following properties:

- the function return values are identical for identical arguments, and
- the function has no side effects.

The composition of pure functions is also a pure function.
For example, assuming the functions :math:`f` and :math:`g` above are pure, then the composite function :math:`h` will also be pure.

Difficulties with functional programming
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

One drawback to functional programming is that it differs from what many in the HEP community are accustomed to when writing their own physics algorithms.
Commonly used third-party libraries and computing languages can also make functional programming difficult to use in practice.
We argue, though, that physicists often think in terms of functional programming when developing a workflow about the high-level processing steps.
It is not until those processing steps need to be implemented that the functional steps are translated into a different programming paradigm (often *procedural*).

Phlex aims to restore the functional programming approach as the natural way of expressing the data-processing to be performed.
By leveraging commonly used processing patterns (see next section on :ref:`higher-order functions <higher-order-functions>`), any awkwardness due to functional programming is largely alleviated.

.. _higher-order-functions:

Sequences of data and higher-order functions
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Particle physics results are obtained by performing statistical analysis on sequences of data.
Such analysis typically involves repeated invocations of the same kind of operation.
For example, a relatively simple result is calculating the average of :math:`n` numbers:

.. math::
   \overline{b} = \frac{1}{n}\sum_{i \in \mathcal{I}} b_i

where the sum is over a sequence of numbers :math:`(b_i)_{i \in \mathcal{I}}`, and :math:`n` is the size or *cardinality* of the index set :math:`\mathcal{I}` used to identify each element of the sequence.

The sum is an example of a data reduction or *fold*, where a sequence is collapsed into one result.
In particular, the average of :math:`n` numbers can be expressed as:

.. math::
   \overline{b} = \mbox{avg} \left\{(b_i)_{i \in \mathcal{I}}\right\} = \frac{1}{n} \mbox{fold}(+, (b_i)_{i \in \mathcal{I}})

where the fold accepts a binary operator (:math:`+` in this case) that is applied to pairs of (usually consecutive) elements of the provided sequence.

The fold is an example of a *higher-order function* (HOF) [Wiki-hof]_ that accepts a sequence and an operator applied to elements of that sequence.

Additional HOFs exist---for example, suppose the sequence :math:`(b_i)` was created by applying a function :math:`p: A \rightarrow B` to each element of a sequence :math:`(a_i)`.
Such a HOF is called a map or *transform*:

.. math::
   (b_i)_{i \in \mathcal{I}} = (p(a_i))_{i \in \mathcal{I}} = \mbox{transform}(p, (a_i)_{i \in \mathcal{I}})

In such a scenario, the average :math:`\overline{b}` could be expressed as:

.. math::
   \overline{b} = \frac{1}{n} \mbox{fold}(+, \mbox{transform}(p, (a_i)_{i \in \mathcal{I}}))

A calculation is then generally expressed in terms of:

1. The HOFs to be used (:math:`\mbox{fold}`, :math:`\mbox{transform}`, etc.)
2. The operation to be used by each HOF (:math:`+`, :math:`p`, etc.)
3. The sequence(s) of data on which the HOFs are to be applied.

Such a formulation lends itself to well-established processing patterns can be naturally factorized and parallelized.

Higher-order functions supported by Phlex
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

In general, higher-order functions transform one sequence to another:

.. math::
   (a_{i_1i_2\dots i_n}) \rightarrow (b_{j_1j_2\dots j_m})

where the multiple indices indicate that the sequences can be multidimensional.
Note that :math:`n` is not necessarily equal to :math:`m`.

The following table lists the higher-order functions supported by Phlex.
Details of each higher-order function will be given in the corresponding sections in the User API section.

+---------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------+
| Higher-order function                                                                                                           | Resulting sequence                                |
+------------------+-----------------------------------------+--------------------------------------------------------------------+----------------------------+----------------------+
| Name             | Operator                                | Sequence transformation                                            | Dimension                  | Length               |
+==================+=========================================+====================================================================+============================+======================+
| Transform        | :math:`f: A \rightarrow B`              | .. math::                                                          | :math:`\dim(b) = \dim(a)`  | :math:`|b| = |a|`    |
|                  |                                         |    \underbrace{(a_{i_1\dots i_n})}_a \rightarrow                   |                            |                      |
|                  |                                         |    \underbrace{(b_{i_1\dots i_n})}_b                               |                            |                      |
+------------------+-----------------------------------------+--------------------------------------------------------------------+----------------------------+----------------------+
| Fold             | :math:`g: C \times D \rightarrow D`     | .. math::                                                          | :math:`\dim(d) < \dim(c)`  | :math:`|d| < |c|`    |
|                  |                                         |    \underbrace{(c_{i_1\dots i_n})}_c \rightarrow                   |                            |                      |
|                  |                                         |    \underbrace{(d_{i_1\dots i_m})}_d                               |                            |                      |
+------------------+-----------------------------------------+--------------------------------------------------------------------+----------------------------+----------------------+
| Unfold           | .. math::                               | .. math::                                                          | :math:`\dim(c) > \dim(d)`  | :math:`|c| > |d|`    |
|                  |    p: D &\rightarrow& \mbox{Boolean} \\ |    \underbrace{(d_{i_1\dots i_m})}_d \rightarrow                   |                            |                      |
|                  |    q: D &\rightarrow& D \times C        |    \underbrace{(c_{i_1\dots i_n})}_c                               |                            |                      |
+------------------+-----------------------------------------+--------------------------------------------------------------------+----------------------------+----------------------+
| Transform        | :math:`p: A \rightarrow \mbox{Boolean}` | .. math::                                                          | :math:`\dim(a') = \dim(a)` | :math:`|a'| \le |a|` |
|                  |                                         |    \underbrace{(a_{i_1\dots i_n})}_a \rightarrow                   |                            |                      |
|                  |                                         |    \underbrace{(a_{i_1\dots i_n})}_{a'}                            |                            |                      |
+------------------+-----------------------------------------+--------------------------------------------------------------------+----------------------------+----------------------+
| Observer         | :math:`p: A \rightarrow \mathbb{1}`     | .. math::                                                          |                            | :math:`|b| = 0`      |
|                  |                                         |    \underbrace{(a_{i_1\dots i_n})}_a \rightarrow                   |                            |                      |
|                  |                                         |    \underbrace{\emptyset}_b                                        |                            |                      |
+------------------+-----------------------------------------+--------------------------------------------------------------------+----------------------------+----------------------+
| Zip              |                                         | .. math::                                                          | .. math::                  | .. math::            |
|                  |                                         |    (\underbrace{(a_{i_1\dots i_n})}_a,                             |    \dim(a)                 |    |c|               |
|                  |                                         |     \underbrace{(b_{i_1\dots i_n})}_b)                             |            = \dim(b)       |     = \min(|a|, |b|) |
|                  |                                         |      \rightarrow                                                   |            = \dim(c)       |                      |
|                  |                                         |      \underbrace{((a_{i_1\dots i_n}, b_{i_1\dots i_n}))}_c         |                            |                      |
+------------------+-----------------------------------------+--------------------------------------------------------------------+----------------------------+----------------------+
| Sliding window   | :math:`s: A \times A \rightarrow B`     | *To be completed*                                                                                                      |
+------------------+-----------------------------------------+--------------------------------------------------------------------+----------------------------+----------------------+


.. rubric:: Footnotes

.. [#f1] As discussed :ref:`here <graph-processing>`, the general topology of a data-processing workflow is a *graph* of functions.

.. rubric:: References

.. [Wiki-pure] https://en.wikipedia.org/wiki/Pure_function
.. [Wiki-hof] https://en.wikipedia.org/wiki/Higher-order_function
