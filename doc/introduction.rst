************
Introduction
************

The following diagram illustrates three high-level computing stages commonly used in HEP to obtain physics results from detector signals.

.. graphviz:: graphviz/framework-scope.gv

Wikipedia decently defines a software framework as [Wiki-framework]_:

  *an abstraction in which software, providing generic functionality, can be selectively changed by additional user-written code, thus providing application-specific software.*

In a HEP context, a user “plugs in” their code to a framework, often through dynamically loaded libraries called *plugins*.
Although not required, this often means that the framework provides a program's `main(...)` function, which (directly or indirectly) invokes user code as configured at appropriate points in the program's execution.

Frameworks are typically used in a high-level trigger environment, for reconstructing physics objects from detector signals, or for simulating physics processes.
Many analysis needs can also be met by a data-processing framework.
However, the HEP community tends to perform final-stage analysis using standalone applications.
Phlex, therefore, aims to satisfy the data-processing needs of only physics reconstruction and simulation.

Requirements process
====================

.. admonition:: Chris Green
   :class: admonition-chg

   Do we need to cite an introductory source that explains these concepts, or are we assuming familiarity?

Phlex is designed to meet *stakeholder requirements* that are established and owned by the DUNE experiment.
The Phlex design may additionally satisfy *system requirements* in support of the stakeholder requirements [#f1]_.

.. admonition:: Chris Green
   :class: admonition-chg

   Apparently there is a Sphinx extension `Sphinx-Needs <https://sphinxcontrib-needs.readthedocs.io/en/latest/>`__ which may help with referring to and cross-referencing requirements, etc.

The stakeholder requirements are listed in :ref:`an appendix <requirements:Framework requirements>` for convenience.
To more easily connect the design to the requirements, any design aspect influenced by specific requirements contains bracketed references to those requirements (e.g. :dune:`1 Algorithm Decomposability`).

Framework philosophy
====================

A framework is a tool that aids the scientific process of inferring accurate physics results from observed data.
Maintaining data integrity is therefore paramount, as is retaining an accounting of how physics results were obtained from that data.
The Phlex design therefore:

- treats all data presented to (or created by) Phlex as immutable for the remainder of a Phlex program's execution,
- requires recording the :term:`provenance` of every created :term:`data product` :dune:`51 Provenance discovery`, and
- enables, and---to the extent possible---ensures the :term:`reproducible` creation of data products.

Programming languages
=====================

The framework will support user :term:`algorithms <algorithm>` written in multiple programming languages :dune:`5 Support for multiple programming languages`.  Specifically, an algorithm may be written in either C++ (no standard yet specified) :dune:`5.1 Support C++ algorithms` or Python (no version yet specified) :dune:`5.2 Support Python algorithms`.
If there is a need to support user algorithms written in another programming language, a corresponding stakeholder requirement should be created.

Note that the language is left unspecified for the implementation of the framework itself.

.. rubric:: Footnotes

.. [#f1] It is possible for additional experiments to become stakeholders of the Phlex framework.
         In such a case, the stakeholder requirements of one experiment cannot negate those of another (particularly DUNE).

.. only:: html

   .. rubric:: References

.. [Wiki-framework] https://en.wikipedia.org/wiki/Software_framework
