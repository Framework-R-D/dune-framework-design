HOF operators
=============

Transforms
----------

+----------------------------+--------------------------------------------------+-----------------------------------------------+
| **Transform**                                                                 | **Resulting sequence**                        |
+----------------------------+--------------------------------------------------+---------------------------+-------------------+
| Operator                   | Sequence transformation                          | Dimension                 | Length            |
+============================+==================================================+===========================+===================+
| :math:`f: A \rightarrow B` | .. math::                                        | :math:`\dim(b) = \dim(a)` | :math:`|b| = |a|` |
|                            |    :no-wrap:                                     |                           |                   |
|                            |                                                  |                           |                   |
|                            |    \(                                            |                           |                   |
|                            |    \underbrace{(a_{i_1\dots i_n})}_a \rightarrow |                           |                   |
|                            |    \underbrace{(b_{i_1\dots i_n})}_b             |                           |                   |
|                            |    \)                                            |                           |                   |
+----------------------------+--------------------------------------------------+---------------------------+-------------------+

**Return type**: A transform algorithm may create multiple data products by returning an :cpp:`std::tuple<T1, ..., Tn>`  where each of the types :cpp:`T1, ..., Tn` models a data-product created type.

Filters and predicates
----------------------

+--------------------------------------------------------------------------------------------+---------------------------------------------------+
| **Filter**                                                                                 | **Resulting sequence**                            |
+-----------------------------------------+--------------------------------------------------+----------------------------+----------------------+
| Operator (predicate)                    | Sequence transformation                          | Dimension                  | Length               |
+=========================================+==================================================+============================+======================+
| :math:`p: A \rightarrow \text{Boolean}` | .. math::                                        | :math:`\dim(a') = \dim(a)` | :math:`|a'| \le |a|` |
|                                         |    :no-wrap:                                     |                            |                      |
|                                         |                                                  |                            |                      |
|                                         |    \(                                            |                            |                      |
|                                         |    \underbrace{(a_{i_1\dots i_n})}_a \rightarrow |                            |                      |
|                                         |    \underbrace{(a_{i_1\dots i_n})}_{a'}          |                            |                      |
|                                         |    \)                                            |                            |                      |
+-----------------------------------------+--------------------------------------------------+----------------------------+----------------------+

Any user-defined algorithm or output sink may be configured to operate on data that satisfy a Boolean condition or *predicate*.
The act of restricting the invocation of a function to data that satisfy a predicate is known as *filtering*.
To filter data as presented to a given algorithm, one or more predicates must be specified in a *filter clause*.
Phlex will not schedule a predicate for execution if it is not bound to a filter.

.. todo::

   Define filter clause.
   Many algorithms can specify the same predicate in their filter clauses without executing the predicate multiple times.

Phlex will only schedule a filter for execution if there is at least one non-filter algorithm or output sink downstream of it.
Predicates can be evaluated on (e.g.) run-level data-product sets and applied to algorithms that process data from data-product sets that are subsets of the run (e.g. events).

Observers
---------

+-----------------------------------------------------------------------------------------+-----------------------------------------------+
| **Observer**                                                                            | **Resulting sequence**                        |
+--------------------------------------+--------------------------------------------------+----------------------------+------------------+
| Operator                             | Sequence transformation                          | Dimension                  | Length           |
+======================================+==================================================+============================+==================+
| :math:`p: A \rightarrow \mathbbm{1}` | .. math::                                        | :math:`\dim(a') = \dim(a)` | :math:`|a'| = 0` |
|                                      |    :no-wrap:                                     |                            |                  |
|                                      |                                                  |                            |                  |
|                                      |    \(                                            |                            |                  |
|                                      |    \underbrace{(a_{i_1\dots i_n})}_a \rightarrow |                            |                  |
|                                      |    \underbrace{(\quad)}_{a'}                     |                            |                  |
|                                      |    \)                                            |                            |                  |
+--------------------------------------+--------------------------------------------------+----------------------------+------------------+

As mentioned in :numref:`functional_programming:Higher-order functions supported by Phlex`, observers are a special case of filters that always reject the data presented to them.
Because of this, in a purely functional approach, it is unnecessary to invoke an observer as no data will be produced by an observer.
Additionally, any algorithms downstream of an always-rejecting filter will never be invoked.

However, there are cases where a user may wish to inspect a data product without adjusting the data flow of the program.
This is done by creating an algorithm called an *observer*, which may access a data product but create no data products.
An example of this is writing ROOT histograms or trees that are not intended to be used in another framework program.

Unlike filters and predicates, observers (by definition) are allowed to be the most downstream algorithms of the graph.

Folds
-----

+----------------------------------------------------------------------------------------+-------------------------------------------------+
| **Fold**                                                                               | **Resulting sequence**                          |
+-------------------------------------+--------------------------------------------------+---------------------------+---------------------+
| Operator                            | Sequence transformation                          | Dimension                 | Length              |
+=====================================+==================================================+===========================+=====================+
| :math:`g: C \times D \rightarrow D` | .. math::                                        | :math:`\dim(d) < \dim(c)` | :math:`|d| \le |c|` |
|                                     |    :no-wrap:                                     |                           |                     |
|                                     |                                                  |                           |                     |
|                                     |    \(                                            |                           |                     |
|                                     |    \underbrace{(c_{i_1\dots i_n})}_c \rightarrow |                           |                     |
|                                     |    \underbrace{(d_{i_1\dots i_m})}_d             |                           |                     |
|                                     |    \)                                            |                           |                     |
+-------------------------------------+--------------------------------------------------+---------------------------+---------------------+

Unfolds
-------

+--------------------------------------------------------------------------------------------+-------------------------------------------------+
| **Unfold**                                                                                 | **Resulting sequence**                          |
+-----------------------------------------+--------------------------------------------------+---------------------------+---------------------+
| Operators                               | Sequence transformation                          | Dimension                 | Length              |
+=========================================+==================================================+===========================+=====================+
| :math:`p: D \rightarrow \text{Boolean}` | .. math::                                        | :math:`\dim(c) > \dim(d)` | :math:`|c| \ge |d|` |
|                                         |    :no-wrap:                                     |                           |                     |
+-----------------------------------------+                                                  |                           |                     |
| :math:`q: D \rightarrow D \times C`     |    \(                                            |                           |                     |
|                                         |    \underbrace{(d_{i_1\dots i_m})}_d \rightarrow |                           |                     |
|                                         |    \underbrace{(c_{i_1\dots i_n})}_c             |                           |                     |
|                                         |    \)                                            |                           |                     |
+-----------------------------------------+--------------------------------------------------+---------------------------+---------------------+

Unfolds are the opposite of folds, where the output sequence is larger than the input sequence :dune:`17 Unfolding data products`.
An unfold can be used for parallelizing the processing of a data product in smaller chunks.

.. todo:: Explain predicate unfolds here.

Composite CHOFs
---------------
