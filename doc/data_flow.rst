Data flow
=========

In the :ref:`description of functional programming <programming_paradigm:Functional programming>`, the example was given for creating tracks from wires.
The simplified expression for doing this was the chained application of two functions :math:`f` and :math:`g` such that:

.. math::
   ts = g(f(ws)) = (g \circ f)(ws)

where :math:`ws` and :math:`ts` are the wires and tracks, respectively.

An alternative representation to the equational form is a *directed graph*

.. graphviz:: graphviz/functional-programming-data-flow.gv
   :align: center

where the functions :math:`f` and :math:`g` are vertices or *nodes* and the data :math:`ws` and :math:`ts` are passed along arrows or *edges* that connect the nodes [#f1]_.
The arrows indicate the flow of the data (or *data flow*) through the graph.

Some observations:

- The function :math:`f` returns hits that are unlabeled in the equational form.
  For the graph above, we explicitly label those hits as :math:`hs` to emphasize that data are always passed along edges.
  If, however, the hits are not needed by any other function in the graph, the two functions :math:`f` and :math:`g` can be replaced by their composition :math:`h=g \circ f`

  .. graphviz:: graphviz/functional-programming-data-flow-optimized.gv
     :align: center

  resulting in potential performance improvements in computational efficiency and program memory usage.

- A directed graph can have no unterminated edges---i.e. an edge must have a source (the tail of the arrow) and a target (the head of the arrow).
  This means that whereas the equation does not need to specify where the :math:`ws` wires originate (or where the :math:`ts` tracks end up), such locations must be specified in the graph.
  Any node that has only outgoing edges is called a *source* (denoted by a solid dot), and any node that has only incoming edges is a *sink* (denoted by an encircled solid dot).

Data flow with sequences
------------------------

As :ref:`mentioned earlier <programming_paradigm:Sequences of data and higher-order functions>`, processing sequences of data is a critical aspect of obtaining physics results.
The data-flow discussion in the previous section naturally maps to applying the functions :math:`f` and :math:`g` to elements of sequences.  Specifically [#f2]_:

- Instead of the individual objects :math:`ws`, :math:`hs`, and :math:`ts` being passed along the edges, the sequences :math:`(ws_i)`, :math:`(hs_i)`, and :math:`(ts_i)` are passed.
- The functions :math:`f` and :math:`g` map to :math:`\mbox{transform}\left\{f\right\}` and :math:`\mbox{transform}\left\{g\right\}`, respectively.

.. graphviz:: graphviz/functional-programming-data-flow-hof.gv
   :align: center

The above graph does not specify an implementation---assuming :math:`f` and :math:`g` are :ref:`pure functions<programming_paradigm:Pure functions>`, the same result is obtained if (a) full sequences are passed between the nodes, or (b) one element per sequence is passed at a time.
Whether option (a) or (b) is chosen as the processing implementation depends on the data and the overall constraints on the program.

.. admonition:: Chris Green
   :class: admonition-chg

   Is this decided by the framework itself, by user code or by configuration?

One benefit to using a graph representation using data sequences and higher-order functions is the ability to easily express folds and unfolds.
As an illustration, consider the calculation of a sum of squares for all integers from 1 through :math:`n`:

.. math::
   S(n) = \sum_{i=1}^n i^2

This calculation requires three separate steps:

1. an unfold called *iota* that, given an integer :math:`n`, generates a sequence of integers from 1 through :math:`n`,
2. a transformation called *square* that squares each integer in the sequence, and
3. a fold called *sum* that sums all squared integers.

The data-flow graph of individual objects looks like:

.. graphviz:: graphviz/unfold-transform-fold.gv
   :align: center

where each number is passed along its own edge to the nodes performing the calculation.
By adopting a sequence-based representation of the sum-of-squares problem, the data-flow graph is considerably simplified:

.. graphviz:: graphviz/unfold-transform-fold-hof.gv
   :align: center

In addition, the topology of the sequence-based graph remains the same regardless of the value of :math:`n`; the topology of the object-based graph becomes intractable as :math:`n` increases.

The vast majority of graphs included in this design document adopt the sequence-based data-flow representation.

.. rubric:: Footnotes

.. [#f1] Treating functions as nodes and data as edges is a function-centric view of the graph.
         It is also possible to invert the view of the graph such that the data are treated as nodes and the functions as edges; this is the data-centric graph, which is the *line digraph* of the function-centric graph.
.. [#f2] In Haskell (and, correspondingly, in category theory), this transformation is achieved through the `List` functor.
