*****************
Conceptual design
*****************

.. admonition:: Purpose

   The conceptual design is not a reference manual; it is a high-level description of how the framework aims to satisfy the :ref:`requirements <requirements:Framework requirements>`.
   The audience for the conceptual design is the physicist, algorithm author, or framework program runner.
   A more technical description of the intended design is given :ref:`here <technical_design:Technical design>`.

.. admonition:: Chris Green
   :class: admonition-chg

   In general, I would suggest avoiding generic reference labels like "here," or "link."

Preliminaries
=============

Phlex is inspired by *functional programming* and *data-flow graphs*, which are described below in more detail.

.. toctree::
   :maxdepth: 2

   programming_paradigm
   data_flow

Public interface
================

To motivate the public interface, we first discuss how a Phlex data-flow graph is built or, equivalently, how work is scheduled to be performed by Phlex.
We then move on to the ingredients of the data flow, such as data organization and algorithms.
Lastly, we cover how a Phlex program configuration is used to express the desired data flow.

.. toctree::
   :maxdepth: 2

   scheduling
   data_organization
   algorithms
   sources_sinks
   resources
   user_configuration
