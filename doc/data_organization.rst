Data organization
=================

Data products
-------------

.. todo:: Describe what defining data products means.

Framework users are expected to define their own data products :dune:`11.1 Definition of data products`.

Phlex does not require that the in-memory representation of a data product shall be the same as its persistent representation :dune:`2 Data Product Representation`.
In some cases, it may even be advantageous to have multiple in-memory representations for the same data product.

.. todo:: Should we include a section on how to have different representations of the same data product?

Data product identifiers
^^^^^^^^^^^^^^^^^^^^^^^^

Fields required for identifying data products from which to create a sequence:

- data category
- product type
- phase
- creator
- name

Data categories, families, and data-product sets
------------------------------------------------

The following diagram illustrates the difference between data categories, data families, and data-product sets, and the relationships between them :dune:`11.1 Definition of data products,11.2 Creation of data sets,11.3 Definition of data families,11.4 Definition of data family hierarchies`.

.. graphviz:: graphviz/data-organization.gv

Data-product lookup policies
----------------------------
