Framework requirements
======================

**Requirements norm**: Baseline 1 (created March 03, 2025)

1 Algorithm Decomposability
---------------------------

| Jama Connect entry: `DUNE STKH #1 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14536>`__
| See :ref:`scheduling:Building the data-flow graph`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall allow the execution of multiple   |
    |              | algorithms.                                           |
    +==============+=======================================================+
    | Notes        | This is ID #01 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | General, Original                                     |
    +--------------+-------------------------------------------------------+

1.1 Algorithm Communication Via Data Products
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

| Jama Connect entry: `DUNE STKH #111 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14847>`__
| See :ref:`scheduling:Building the data-flow graph`, :ref:`algorithms:Framework registration`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall mediate communication between     |
    |              | algorithms via data products                          |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | General, Reproducibility, Provenance                  |
    +--------------+-------------------------------------------------------+

2 Data Product Representation
-----------------------------

| Jama Connect entry: `DUNE STKH #2 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14539>`__
| See :ref:`data_organization:Data products`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall separate the persistent           |
    |              | representation of data products from their in-memory  |
    |              | representations as seen by algorithms.                |
    +==============+=======================================================+
    | Notes        | This is ID #02 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, General, Accelerators                       |
    +--------------+-------------------------------------------------------+

3 Full utilization of DUNE computing resources
----------------------------------------------

Jama Connect entry: `DUNE STKH #8 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14548>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall run on widely-used scientific     |
    |              | computing systems in order to fully utilize DUNE      |
    |              | computing resources.                                  |
    +==============+=======================================================+
    | Notes        | This is ID #05 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | General, Original, Reproducibility                    |
    +--------------+-------------------------------------------------------+

4 Algorithm hardware requirements
---------------------------------

| Jama Connect entry: `DUNE STKH #9 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14549>`__
| See :ref:`algorithms:Framework registration`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall provide an API that allows users  |
    |              | to express hardware requirements of the algorithms.   |
    +==============+=======================================================+
    | Notes        | This is ID #06 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | General, Original, Reproducibility                    |
    +--------------+-------------------------------------------------------+

4.1 Algorithms can use a GPU
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #11 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14551>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support running algorithms that   |
    |              | require a GPU.                                        |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | General, Accelerators, Reproducibility                |
    +--------------+-------------------------------------------------------+

4.2 Shut down upon unmet algorithm hardware requirements
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #13 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14553>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall shut down if the platform fails   |
    |              | to meet each specified hardware requirement.          |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | General                                               |
    +--------------+-------------------------------------------------------+

4.3 Emit diagnostic upon unmet algorithm hardware requirements
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #112 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14885>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall emit a diagnostic message for     |
    |              | each hardware requirement the platform fails to meet. |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | General                                               |
    +--------------+-------------------------------------------------------+

5 Support for multiple programming languages
--------------------------------------------

| Jama Connect entry: `DUNE STKH #14 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14554>`__
| See :ref:`introduction:Programming languages`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support the invocation of         |
    |              | algorithms written in multiple programming languages. |
    +==============+=======================================================+
    | Notes        | This is ID #07 from the original DUNE document.       |
    |              |                                                       |
    |              | If DUNE decides that additional languages should be   |
    |              | supported in the future, a specific requirement can   |
    |              | be added for that language as a sub-requirement.      |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, General                                     |
    +--------------+-------------------------------------------------------+

5.1 Support C++ algorithms
^^^^^^^^^^^^^^^^^^^^^^^^^^

| Jama Connect entry: `DUNE STKH #81 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14663>`__
| See :ref:`introduction:Programming languages`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support the invocation of         |
    |              | algorithms written in C++.                            |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | General                                               |
    +--------------+-------------------------------------------------------+

5.2 Support Python algorithms
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

| Jama Connect entry: `DUNE STKH #82 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14664>`__
| See :ref:`introduction:Programming languages`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support the invocation of         |
    |              | algorithms written in Python.                         |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | General                                               |
    +--------------+-------------------------------------------------------+

6 Provide instructions for writing algorithms in supported languages
--------------------------------------------------------------------

Jama Connect entry: `DUNE STKH #16 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14556>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework documentation shall provide             |
    |              | instructions for writing framework-executable         |
    |              | algorithms in supported languages.                    |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Documentation                                         |
    +--------------+-------------------------------------------------------+

7 Persist user-defined metadata
-------------------------------

Jama Connect entry: `DUNE STKH #17 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14557>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall provide user-accessible           |
    |              | persistence of user-defined metadata.                 |
    +==============+=======================================================+
    | Notes        | This is ID #08 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | General, Original                                     |
    +--------------+-------------------------------------------------------+

8 Framework shall read its own output files
-------------------------------------------

Jama Connect entry: `DUNE STKH #19 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14560>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall provide the ability to read a     |
    |              | framework-produced file as input to a subsequent      |
    |              | framework job so that the physics data are equivalent |
    |              | to the physics data obtained from a single execution  |
    |              | of the combined job.                                  |
    +==============+=======================================================+
    | Notes        | This is ID #10 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Physics Analysis, Original                            |
    +--------------+-------------------------------------------------------+

9 Presenting data to subsequent algorithms
------------------------------------------

| Jama Connect entry: `DUNE STKH #20 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14562>`__
| See :ref:`scheduling:Building the data-flow graph`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall present data produced by an       |
    |              | already executed algorithm to each subsequent,        |
    |              | requesting algorithm.                                 |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Physics Analysis                                      |
    +--------------+-------------------------------------------------------+

10 Mix input streams
--------------------

Jama Connect entry: `DUNE STKH #21 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14563>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support the creation of data sets |
    |              | composed of data products derived from data           |
    |              | originating from disparate input sources.             |
    +==============+=======================================================+
    | Notes        | This is ID #11 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Physics Analysis, Original                            |
    +--------------+-------------------------------------------------------+

11 Flexible data units
----------------------

Jama Connect entry: `DUNE STKH #22 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14580>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support flexibly defined,         |
    |              | context-aware processing units to address the varying |
    |              | granularity necessary for processing different kinds  |
    |              | of data.                                              |
    +==============+=======================================================+
    | Notes        | This is ID #12 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Flexible Processing Unit (FPU)              |
    +--------------+-------------------------------------------------------+

11.1 Definition of data products
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

| Jama Connect entry: `DUNE STKH #85 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14693>`__
| See :ref:`data_organization:Data products`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall provide the ability for           |
    |              | user-level code to define data products.              |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Flexible Processing Unit (FPU)                        |
    +--------------+-------------------------------------------------------+

11.2 Creation of data sets
^^^^^^^^^^^^^^^^^^^^^^^^^^

| Jama Connect entry: `DUNE STKH #86 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14696>`__
| See :ref:`data_organization:Data categories, families, and data-product sets`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall provide the ability for           |
    |              | user-level code to create new data sets.              |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Flexible Processing Unit (FPU)                        |
    +--------------+-------------------------------------------------------+

11.3 Definition of data families
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

| Jama Connect entry: `DUNE STKH #87 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14697>`__
| See :ref:`data_organization:Data categories, families, and data-product sets`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall provide the ability for           |
    |              | user-level code to define data families.              |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Flexible Processing Unit (FPU)                        |
    +--------------+-------------------------------------------------------+

11.4 Definition of data family hierarchies
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

| Jama Connect entry: `DUNE STKH #88 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14698>`__
| See :ref:`data_organization:Data categories, families, and data-product sets`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall provide the ability for           |
    |              | user-level code to define hierarchies of data         |
    |              | families.                                             |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Flexible Processing Unit (FPU)                        |
    +--------------+-------------------------------------------------------+

12 Data product I/O independence
--------------------------------

Jama Connect entry: `DUNE STKH #24 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14583>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support reading from disk only    |
    |              | the data products required by a given algorithm.      |
    +==============+=======================================================+
    | Notes        | This is ID #14 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Data I/O layer                              |
    +--------------+-------------------------------------------------------+

13 Process collections of unconstrained size
--------------------------------------------

Jama Connect entry: `DUNE STKH #25 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14584>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support processing of collections |
    |              | that are too large to fit into memory at one time.    |
    +==============+=======================================================+
    | Notes        | This originates from ID #16 from the original DUNE    |
    |              | document.                                             |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Flexible Processing Unit (FPU)              |
    +--------------+-------------------------------------------------------+

13.1 Read collections of unconstrained size
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #32 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14592>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support the reading of            |
    |              | collections too large to hold in memory.              |
    +==============+=======================================================+
    | Notes        | This is ID #57 from the original DUNE document.       |
    |              |                                                       |
    |              | Very large data collections could be 10s of GBs in    |
    |              | size, and the memory budget may be a maximum of a few |
    |              | GBs.                                                  |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Memory management                           |
    +--------------+-------------------------------------------------------+

13.2 Write collections of unconstrained size
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #120 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15288>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support the writing of            |
    |              | collections too large to hold in memory.              |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Memory management                           |
    +--------------+-------------------------------------------------------+

14 Configuration comparison
---------------------------

Jama Connect entry: `DUNE STKH #98 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14724>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall provide the ability to compare    |
    |              | two configurations.                                   |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Configuration                                         |
    +--------------+-------------------------------------------------------+

15 Record execution environment
-------------------------------

Jama Connect entry: `DUNE STKH #30 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14590>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall record the job's execution        |
    |              | environment.                                          |
    +==============+=======================================================+
    | Notes        | This is ID #20 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Reproducibility, Provenance                 |
    +--------------+-------------------------------------------------------+

15.1 User-selectable list of recordable execution environment components
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #100 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14730>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall provide the list of recordable    |
    |              | components of the execution environment.              |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Reproducibility, Provenance                           |
    +--------------+-------------------------------------------------------+

15.2 Save user-selected execution environment components
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #101 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14731>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall save each execution-environment   |
    |              | description selected by the user from the             |
    |              | framework-provided-list.                              |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Reproducibility, Provenance                           |
    +--------------+-------------------------------------------------------+

15.2.1 Record user-selected items from the shell environment
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Jama Connect entry: `DUNE STKH #123 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15480>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall record user-selected items from   |
    |              | the shell environment.                                |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Provenance                                            |
    +--------------+-------------------------------------------------------+

15.3 User-provided execution environment information
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #124 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15482>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall record labelled execution         |
    |              | environment information provided by the user.         |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Provenance                                            |
    +--------------+-------------------------------------------------------+

16 Maximum memory usage
-----------------------

Jama Connect entry: `DUNE STKH #31 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14591>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall gracefully shut down if the       |
    |              | program attempts to exceed a configured memory limit. |
    +==============+=======================================================+
    | Notes        | This is ID #59 from the original DUNE document.       |
    |              |                                                       |
    |              | The maximum memory available is a static quantity     |
    |              | that can apply to (a) a job using an entire node with |
    |              | all of its available RSS, and (b) a job using a       |
    |              | specific grid slot with a limit on the RSS.  It is    |
    |              | assumed that the operating system and C++/Python      |
    |              | runtimes are not already enforcing this limit.        |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Memory management, Resource management      |
    +--------------+-------------------------------------------------------+

16.1 Diagnostic message when exceeding memory limit
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #137 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15802>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall emit a diagnostic message if the  |
    |              | program attempts to exceed the configured maximum     |
    |              | memory.                                               |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Memory management, Error handling                     |
    +--------------+-------------------------------------------------------+

17 Unfolding data products
--------------------------

| Jama Connect entry: `DUNE STKH #33 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14593>`__
| See :ref:`algorithms:Unfolds`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall allow the unfolding of data       |
    |              | products into a sequence of finer-grained data        |
    |              | products.                                             |
    +==============+=======================================================+
    | Notes        | This is ID #58 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Memory management, Original, Flexible Processing Unit |
    |              | (FPU)                                                 |
    +--------------+-------------------------------------------------------+

18 Access to external data sources
----------------------------------

Jama Connect entry: `DUNE STKH #35 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14595>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support access to external data   |
    |              | sources.                                              |
    +==============+=======================================================+
    | Notes        | This is ID #47 from the original DUNE document.       |
    |              |                                                       |
    |              | By "external data sources," we mean "data sources     |
    |              | **other than** framework-readable data files          |
    |              | containing detector readout or simulated physics      |
    |              | data."                                                |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Services                                    |
    +--------------+-------------------------------------------------------+

18.1 Calibration database algorithms
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #40 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14600>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support algorithms that provide   |
    |              | data from calibration databases.                      |
    +==============+=======================================================+
    | Notes        | This is ID #68 as proposed to DUNE.                   |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Services                                              |
    +--------------+-------------------------------------------------------+

19 Algorithm code versioning and build information
--------------------------------------------------

Jama Connect entry: `DUNE STKH #39 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14599>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall have an option to record build    |
    |              | information, including the source code version,       |
    |              | associated with each algorithm.                       |
    +==============+=======================================================+
    | Notes        | This is ID #25 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Reproducibility, Provenance                 |
    +--------------+-------------------------------------------------------+

20 Algorithms independent of framework interface
------------------------------------------------

| Jama Connect entry: `DUNE STKH #43 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14608>`__
| See :ref:`algorithms:Algorithms`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support the registration of       |
    |              | algorithms that are independent of framework          |
    |              | interface.                                            |
    +==============+=======================================================+
    | Notes        | This is ID #48 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Services, Original                                    |
    +--------------+-------------------------------------------------------+

21 Safely executing thread-safe and non-thread-safe algorithms
--------------------------------------------------------------

Jama Connect entry: `DUNE STKH #45 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14611>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall safely execute user algorithms    |
    |              | declared to be non-thread-safe along with those       |
    |              | declared to be thread-safe.                           |
    +==============+=======================================================+
    | Notes        | This is ID #26 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Concurrency and multithreading              |
    +--------------+-------------------------------------------------------+

22 Intra-algorithm concurrency and multi-threading
--------------------------------------------------

| Jama Connect entry: `DUNE STKH #46 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14612>`__
| See :ref:`technical_design:Task management`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall allow algorithms to use the same  |
    |              | parallelism mechanisms the framework uses to schedule |
    |              | the execution of algorithms.                          |
    +==============+=======================================================+
    | Notes        | This is ID #27 from the original DUNE document.       |
    |              |                                                       |
    |              | It is the responsibility of the algorithm author to   |
    |              | ensure that any parallelism libraries used can work   |
    |              | compatibly with those used by the framework itself.   |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Concurrency and multithreading              |
    +--------------+-------------------------------------------------------+

23 Resource specification for the program
-----------------------------------------

| Jama Connect entry: `DUNE STKH #47 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14613>`__
| See :ref:`user_configuration:Program resource specification`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall enable the specification of       |
    |              | resources required by the program.                    |
    +==============+=======================================================+
    | Notes        | This is ID #28 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Concurrency and multithreading, Resource    |
    |              | management                                            |
    +--------------+-------------------------------------------------------+

23.1 Specification of maximum number of CPU threads
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #146 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15865>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall enable the specification of the   |
    |              | maximum number of CPU threads permitted by the        |
    |              | program.                                              |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Resource management                                   |
    +--------------+-------------------------------------------------------+

23.2 Specification of maximum allowed CPU memory
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #147 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15866>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall enable the specification of the   |
    |              | maximum CPU memory allowed by the program.            |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Resource management, Memory management                |
    +--------------+-------------------------------------------------------+

23.3 Specification of GPU resources
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #148 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15869>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall enable the specification of GPU   |
    |              | resources required by the program.                    |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Resource management                                   |
    +--------------+-------------------------------------------------------+

23.4 Specification of user-defined resources
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #149 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15871>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall enable the specification of       |
    |              | user-defined resources required by the program.       |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Resource management                                   |
    +--------------+-------------------------------------------------------+

24 Resource specification for algorithms
----------------------------------------

Jama Connect entry: `DUNE STKH #52 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14620>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall enable the specification of       |
    |              | resources required by each algorithm.                 |
    +==============+=======================================================+
    | Notes        | This is ID #33 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Concurrency and multithreading, Resource    |
    |              | management                                            |
    +--------------+-------------------------------------------------------+

24.1 Serial access to a thread-unsafe resource
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #145 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15856>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall permit algorithm authors to       |
    |              | specify that the algorithm requires serial access to  |
    |              | a thread-unsafe resource.                             |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Concurrency and multithreading, Original, Resource    |
    |              | management                                            |
    +--------------+-------------------------------------------------------+

24.2 Specification of algorithm's maximum number of CPU threads
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

| Jama Connect entry: `DUNE STKH #152 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15883>`__
| See :ref:`algorithms:Framework registration`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall enable the specification of the   |
    |              | maximum number of CPU threads permitted by the        |
    |              | algorithm.                                            |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Resource management                                   |
    +--------------+-------------------------------------------------------+

24.3 Specification of algorithm's CPU memory usage
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #154 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15889>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall enable the specification of an    |
    |              | algorithm's expected CPU memory usage.                |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Resource management, Memory management                |
    +--------------+-------------------------------------------------------+

24.4 Specification of algorithm's GPU resources
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #153 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15886>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall enable the specification of GPU   |
    |              | resources required by the algorithm.                  |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Resource management                                   |
    +--------------+-------------------------------------------------------+

24.4.1 Remote GPU algorithm support
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Jama Connect entry: `DUNE STKH #42 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14607>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support algorithms that perform   |
    |              | calculations using a remote GPU.                      |
    +==============+=======================================================+
    | Notes        | This is ID #70 as proposed to DUNE.                   |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Services                                              |
    +--------------+-------------------------------------------------------+

24.4.2 Local GPU algorithm support
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Jama Connect entry: `DUNE STKH #41 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14602>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support algorithms that perform   |
    |              | calculations using a local GPU.                       |
    +==============+=======================================================+
    | Notes        | This is ID #69 as proposed to DUNE.                   |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Services                                              |
    +--------------+-------------------------------------------------------+

24.5 Specification of algorithm's user-defined resources
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #155 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15891>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall enable the specification of       |
    |              | user-defined resources required by the algorithm.     |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Resource management                                   |
    +--------------+-------------------------------------------------------+

25 Logging resource usage per algorithm invocation
--------------------------------------------------

Jama Connect entry: `DUNE STKH #48 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14614>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support logging the usage of a    |
    |              | specified resource for each algorithm using the       |
    |              | resource.                                             |
    +==============+=======================================================+
    | Notes        | This is ID #29 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Concurrency and multithreading, Resource    |
    |              | management                                            |
    +--------------+-------------------------------------------------------+

25.1 Elapsed time information
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

| Jama Connect entry: `DUNE STKH #60 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14629>`__
| See :ref:`technical_design:Monitoring and reporting`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall have an option to provide elapsed |
    |              | time information for each algorithm executed in a     |
    |              | framework program.                                    |
    +==============+=======================================================+
    | Notes        | This is ID #66 as proposed to DUNE.                   |
    |              |                                                       |
    |              | This option is intended to capture wall-clock time    |
    |              | and not CPU time.  If more granular reporting of CPU  |
    |              | vs. IO time is required, dedicated profiling tools    |
    |              | like VTune or Linaro Forge should be used.            |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | General, Resource management                          |
    +--------------+-------------------------------------------------------+

26 Resource-based algorithm concurrency
---------------------------------------

Jama Connect entry: `DUNE STKH #50 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14618>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall dynamically schedule algorithms   |
    |              | to execute efficiently according to the availability  |
    |              | of each algorithm's required resources.               |
    +==============+=======================================================+
    | Notes        | This is ID #31 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Concurrency and multithreading, Resource    |
    |              | management                                            |
    +--------------+-------------------------------------------------------+

26.1 Efficient execution of algorithms requiring access to a network resource
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #144 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15854>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall efficiently execute a graph of    |
    |              | algorithms where at least one algorithm requires      |
    |              | access to a network resource.                         |
    +==============+=======================================================+
    | Notes        | An example of efficient execution is an algorithm     |
    |              | requiring network resource does not occupy a core     |
    |              | that can do other work while the algorithm "waits"    |
    |              | for the resource to respond.                          |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Concurrency and multithreading, Original, Resource    |
    |              | management                                            |
    +--------------+-------------------------------------------------------+

26.2 Optimize memory management for data products
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #142 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15847>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall optimize the memory management of |
    |              | data products.                                        |
    +==============+=======================================================+
    | Notes        | Optimization means making the data products           |
    |              | available for the shortest period of time possible    |
    |              | for all algorithms that require them.  The framework, |
    |              | however, may need to run in series multiple           |
    |              | algorithms requiring those data products if those     |
    |              | algorithms would run out of resources if run          |
    |              | concurrently.                                         |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Resource management                                   |
    +--------------+-------------------------------------------------------+

26.3 Optimize availability of external resources
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #143 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15848>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall optimize the availability of      |
    |              | external resources.                                   |
    +==============+=======================================================+
    | Notes        | Examples of external resources include local GPUs,    |
    |              | remote inference servers, and databases.              |
    |              |                                                       |
    |              | This requirement also serves as a replacement for a   |
    |              | former requirement: "The framework MUST be able to    |
    |              | broker/cache service replies that might be common to  |
    |              | multiple instances of algorithms (reduce load on      |
    |              | external service/disk/memory/network/...). E.g. a     |
    |              | request for a calibration constant that is common     |
    |              | among all FPUs in a run. Not every instance of an     |
    |              | algorithm should trigger an actual request to the     |
    |              | central database providing these."                    |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Resource management                                   |
    +--------------+-------------------------------------------------------+

26.4 Efficient execution of algorithms with specific CPU memory requirements
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #150 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15874>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall efficiently execute a graph of    |
    |              | algorithms where at least one algorithm specifies a   |
    |              | required amount of CPU memory.                        |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Resource management, Memory management                |
    +--------------+-------------------------------------------------------+

26.5 Efficient execution of algorithms with specific GPU memory requirements
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #151 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15875>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall efficiently execute a graph of    |
    |              | algorithms where at least one algorithm specifies a   |
    |              | required amount of GPU memory.                        |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Resource management, Memory management                |
    +--------------+-------------------------------------------------------+

27 Composable workflows using GPU algorithms and CPU algorithms
---------------------------------------------------------------

Jama Connect entry: `DUNE STKH #54 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14622>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support composable workflows that |
    |              | use GPU algorithms along with CPU algorithms.         |
    +==============+=======================================================+
    | Notes        | This is ID #36 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Concurrency and multithreading, Resource    |
    |              | management                                            |
    +--------------+-------------------------------------------------------+

28 Specification of data products required by an algorithm
----------------------------------------------------------

| Jama Connect entry: `DUNE STKH #65 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14634>`__
| See :ref:`algorithms:Framework registration`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support the specification of data |
    |              | products required as input by an algorithm.           |
    +==============+=======================================================+
    | Notes        | This is ID #63 as proposed to DUNE.                   |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Registration                                          |
    +--------------+-------------------------------------------------------+

29 Specification of data products created by an algorithm
---------------------------------------------------------

| Jama Connect entry: `DUNE STKH #156 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15897>`__
| See :ref:`algorithms:Framework registration`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support the specification of data |
    |              | products created as output by an algorithm.           |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Registration                                          |
    +--------------+-------------------------------------------------------+

30 Emit message describing data flow of program
-----------------------------------------------

Jama Connect entry: `DUNE STKH #68 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14637>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall have an option to emit a          |
    |              | description of the data flow of a configured program  |
    |              | without executing the workflow.                       |
    +==============+=======================================================+
    | Notes        | This is ID #64 as proposed to DUNE.                   |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Concurrency and multithreading                        |
    +--------------+-------------------------------------------------------+

31 Emit message stating algorithm resource requirements
-------------------------------------------------------

Jama Connect entry: `DUNE STKH #56 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14625>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall have an option to emit a message  |
    |              | stating the resources required by each algorithm of a |
    |              | configured program without executing the workflow.    |
    +==============+=======================================================+
    | Notes        | This is ID #38 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Concurrency and multithreading, Resource    |
    |              | management                                            |
    +--------------+-------------------------------------------------------+

32 Monitoring global memory use
-------------------------------

| Jama Connect entry: `DUNE STKH #59 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14628>`__
| See :ref:`technical_design:Monitoring and reporting`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall be able to report the global      |
    |              | memory use of the framework program at user-specified |
    |              | points in time.                                       |
    +==============+=======================================================+
    | Notes        | This is ID #67 as proposed to DUNE.                   |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | General, Memory management, Resource management       |
    +--------------+-------------------------------------------------------+

33 Framework-independent message logging
----------------------------------------

| Jama Connect entry: `DUNE STKH #61 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14630>`__
| See :ref:`technical_design:Logging`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support a logging solution that   |
    |              | is usable in an algorithm without that algorithm      |
    |              | explicitly relying on the framework.                  |
    +==============+=======================================================+
    | Notes        | This is ID #65 as proposed to DUNE.                   |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | General                                               |
    +--------------+-------------------------------------------------------+

34 Configuration validation
---------------------------

Jama Connect entry: `DUNE STKH #64 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14633>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall validate an algorithm's           |
    |              | configuration against specifications provided at      |
    |              | registration time.                                    |
    +==============+=======================================================+
    | Notes        | This is ID #42 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Configuration                               |
    +--------------+-------------------------------------------------------+

35 Algorithm configuration schema availability
----------------------------------------------

Jama Connect entry: `DUNE STKH #67 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14636>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall have an option to emit an         |
    |              | algorithm's configuration schema in human-readable    |
    |              | form.                                                 |
    +==============+=======================================================+
    | Notes        | This is ID #43 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Configuration                               |
    +--------------+-------------------------------------------------------+

36 One configuration per framework execution
--------------------------------------------

Jama Connect entry: `DUNE STKH #69 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14638>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall accept exactly one configuration  |
    |              | per program execution.                                |
    +==============+=======================================================+
    | Notes        | This is ID #44 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Configuration                               |
    +--------------+-------------------------------------------------------+

37 Eager validation of algorithm configuration
----------------------------------------------

Jama Connect entry: `DUNE STKH #70 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14639>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall validate the configuration of     |
    |              | each algorithm before that algorithm processes data.  |
    +==============+=======================================================+
    | Notes        | This is ID #45 from the original DUNE document.       |
    |              |                                                       |
    |              | Validation includes any reading, parsing,             |
    |              | canonicalizing, and checking against applicable       |
    |              | schemata.                                             |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Configuration                               |
    +--------------+-------------------------------------------------------+

38 Framework configuration language
-----------------------------------

Jama Connect entry: `DUNE STKH #72 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14641>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall provide the ability to configure  |
    |              | the execution of a framework program at runtime using |
    |              | a human-readable language.                            |
    +==============+=======================================================+
    | Notes        | This is ID #60 as proposed to DUNE.                   |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Configuration                                         |
    +--------------+-------------------------------------------------------+

39 I/O plugins
--------------

Jama Connect entry: `DUNE STKH #73 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14642>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall provide a public API that enables |
    |              | the implementation of a concrete IO backend for a     |
    |              | specific persistent storage format.                   |
    +==============+=======================================================+
    | Notes        | This is ID #50 from the original DUNE document.       |
    |              |                                                       |
    |              | Data includes physics data and metadata (both         |
    |              | user-provided and framework metadata).                |
    |              |                                                       |
    |              | The goal is to enable non-framework developers to     |
    |              | implement an IO backend without needing to modify the |
    |              | framework itself.                                     |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Data I/O layer, Original                              |
    +--------------+-------------------------------------------------------+

39.1 I/O backend for ROOT
^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #74 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14643>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework ecosystem shall support a ROOT IO       |
    |              | backend.                                              |
    +==============+=======================================================+
    | Notes        | This is ID #51 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Data I/O layer, Original                              |
    +--------------+-------------------------------------------------------+

39.2 I/O backend for HDF5
^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #141 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15838>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework ecosystem shall support an HDF5 IO      |
    |              | backend.                                              |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Data I/O layer, Original                              |
    +--------------+-------------------------------------------------------+

40 Data I/O backward compatibility
----------------------------------

Jama Connect entry: `DUNE STKH #76 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14645>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework IO subsystem shall support backward     |
    |              | compatibility across versions, subject to policy      |
    |              | decisions on deprecation provided by DUNE.            |
    +==============+=======================================================+
    | Notes        | This is ID #54 from the original DUNE document.       |
    |              |                                                       |
    |              | Backward compatibility means that new code is able to |
    |              | read data produced by older versions of the           |
    |              | framework.                                            |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Data I/O layer, Backwards compatibility     |
    +--------------+-------------------------------------------------------+

40.1 Data product backward compatibility
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #106 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14796>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework's IO subsystem shall support backward   |
    |              | compatibility of data products.                       |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Data I/O layer, Backwards compatibility               |
    +--------------+-------------------------------------------------------+

40.2 Metadata backward compatibility
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #107 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14797>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework's IO subsystem shall support backward   |
    |              | compatibility of metadata.                            |
    +==============+=======================================================+
    | Notes        | Metadata here can include user-visible (including     |
    |              | user-provided) metadata, and framework metadata,      |
    |              | which may not be user-visible but is necessary for    |
    |              | framework operation.                                  |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Data I/O layer, Backwards compatibility               |
    +--------------+-------------------------------------------------------+

41 Configurable data compression
--------------------------------

Jama Connect entry: `DUNE STKH #77 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14646>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework IO subsystem shall allow                |
    |              | user-configuration of compression settings for each   |
    |              | concrete IO implementation.                           |
    +==============+=======================================================+
    | Notes        | This is ID #55 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Data I/O layer                              |
    +--------------+-------------------------------------------------------+

42 User-configurable output file rollover
-----------------------------------------

Jama Connect entry: `DUNE STKH #78 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14647>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support user-configurable         |
    |              | rollover of output files.                             |
    +==============+=======================================================+
    | Notes        | This is ID #56 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Data I/O layer                              |
    +--------------+-------------------------------------------------------+

42.1 Output file rollover due to number of data sets in data family
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #109 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14806>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall have an option to rollover output |
    |              | files according to a configurable limit on the number |
    |              | of data sets in a user-specified data family.         |
    +==============+=======================================================+
    | Notes        | Some examples include limiting the output file to     |
    |              | contain data for:                                     |
    |              |                                                       |
    |              | - 1 subrun ("subrun" is the user-specified family)    |
    |              |                                                       |
    |              | - 100 spills ("spill" is the user-specified family)   |
    |              |                                                       |
    |              | - 10 blobs ("blob" is the user-specified family)      |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Data I/O layer                                        |
    +--------------+-------------------------------------------------------+

42.2 Output file rollover due to file size
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #138 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15826>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall have an option to rollover output |
    |              | files according to a configurable limit on            |
    |              | output-file size.                                     |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Data I/O layer                                        |
    +--------------+-------------------------------------------------------+

42.3 Output file rollover due to user-defined quantities
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #139 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15830>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall have an option to rollover output |
    |              | files according to a configurable limit on the        |
    |              | aggregated value of a user-derived quantity.          |
    +==============+=======================================================+
    | Notes        | An example of an aggregated value of a user-derived   |
    |              | quantity is the number of protons on target (POTs).   |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Data I/O layer                                        |
    +--------------+-------------------------------------------------------+

42.4 Output file rollover due to file lifetime
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #140 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15832>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall have an option to rollover output |
    |              | files according to a configurable limit on the time   |
    |              | the file has been open.                               |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Data I/O layer                                        |
    +--------------+-------------------------------------------------------+

43 Algorithm invocation with data products from multiple data sets
------------------------------------------------------------------

Jama Connect entry: `DUNE STKH #89 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14705>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall allow a single invocation of an   |
    |              | algorithm with data products from multiple data sets. |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Flexible Processing Unit (FPU)                        |
    +--------------+-------------------------------------------------------+

43.1 Algorithm invocation with data products from adjacent data sets
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #91 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14713>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support the invocation of an      |
    |              | algorithm with data products belonging to adjacent    |
    |              | data sets.                                            |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Flexible Processing Unit (FPU)                        |
    +--------------+-------------------------------------------------------+

43.1.1 User-defined adjacency
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Jama Connect entry: `DUNE STKH #92 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14714>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support user code that defines    |
    |              | adjacency of data sets within a data family.          |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Flexible Processing Unit (FPU)                        |
    +--------------+-------------------------------------------------------+

44 Algorithm invocation with data products from multiple data families
----------------------------------------------------------------------

Jama Connect entry: `DUNE STKH #113 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14937>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall allow a single invocation of an   |
    |              | algorithm with data products from multiple data       |
    |              | families.                                             |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Flexible Processing Unit (FPU)                        |
    +--------------+-------------------------------------------------------+

45 Specification of algorithm output FPUs
-----------------------------------------

Jama Connect entry: `DUNE STKH #90 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14706>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support the user specification of |
    |              | which data family to place the data products created  |
    |              | by an algorithm.                                      |
    +==============+=======================================================+
    | Notes        | To implement this requirement, the algorithm should   |
    |              | not know where its created data products are          |
    |              | going--that is something that will be specified at    |
    |              | the plugin level (perhaps by configuration).          |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Flexible Processing Unit (FPU)                        |
    +--------------+-------------------------------------------------------+

46 Algorithm-Data Separability
------------------------------

Jama Connect entry: `DUNE STKH #110 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14845>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The data objects exchanged among algorithms shall be  |
    |              | separable from those algorithms.                      |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | General                                               |
    +--------------+-------------------------------------------------------+

47 ProtoDUNE single-phase raw data
----------------------------------

Jama Connect entry: `DUNE STKH #116 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15239>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework ecosystem shall support processing      |
    |              | ProtoDUNE single-phase raw data.                      |
    +==============+=======================================================+
    | Notes        | ProtoDUNE single-phase was used in run 1.             |
    |              |                                                       |
    |              | For this requirement, the framework *ecosystem* is    |
    |              | responsible for processing run 1 data (e.g. the       |
    |              | framework might not read the run 1 data directly, but |
    |              | a translation program might first prepare the run 1   |
    |              | data for reading within the framework).               |
    +--------------+-------------------------------------------------------+
    | Status       | **Deferred**                                          |
    +--------------+-------------------------------------------------------+
    | Tags         | Backwards compatibility, Data I/O layer               |
    +--------------+-------------------------------------------------------+

48 ProtoDUNE dual-phase raw data
--------------------------------

Jama Connect entry: `DUNE STKH #117 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15240>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework ecosystem shall support processing      |
    |              | ProtoDUNE dual-phase raw data.                        |
    +==============+=======================================================+
    | Notes        | ProtoDUNE dual-phase was used in run 1.               |
    |              |                                                       |
    |              | For this requirement, the framework *ecosystem* is    |
    |              | responsible for processing run 1 data (e.g. the       |
    |              | framework might not read the run 1 data directly, but |
    |              | a translation program might first prepare the run 1   |
    |              | data for reading within the framework).               |
    +--------------+-------------------------------------------------------+
    | Status       | **Deferred**                                          |
    +--------------+-------------------------------------------------------+
    | Tags         | Backwards compatibility, Data I/O layer               |
    +--------------+-------------------------------------------------------+

49 ProtoDUNE II horizontal-drift raw data
-----------------------------------------

Jama Connect entry: `DUNE STKH #118 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15242>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework ecosystem shall support processing      |
    |              | ProtoDUNE II horizontal-drift raw data.               |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Backwards compatibility, Data I/O layer               |
    +--------------+-------------------------------------------------------+

50 ProtoDUNE II vertical-drift raw data
---------------------------------------

Jama Connect entry: `DUNE STKH #119 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15244>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework ecosystem shall support processing      |
    |              | ProtoDUNE II vertical-drift raw data.                 |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Backwards compatibility, Data I/O layer               |
    +--------------+-------------------------------------------------------+

51 Provenance discovery
-----------------------

| Jama Connect entry: `DUNE STKH #121 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15293>`__
| See :ref:`introduction:Framework philosophy`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall enable users to discover the      |
    |              | provenance of data products.                          |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Provenance                                            |
    +--------------+-------------------------------------------------------+

51.1 Framework configuration persistency
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #27 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14587>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall provide an option to persist the  |
    |              | configuration of each framework execution to the      |
    |              | output of that execution.                             |
    +==============+=======================================================+
    | Notes        | This is ID #17 from the original DUNE document.       |
    |              |                                                       |
    |              | This requirement is in support of documenting and     |
    |              | reproducing previous results.                         |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Configuration, Reproducibility, Provenance  |
    +--------------+-------------------------------------------------------+

51.2 Framework recording of metadata for reproduction of output data
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #28 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14588>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall record metadata to output         |
    |              | enabling the reproduction of the processing steps     |
    |              | used to produce the data recorded in that output.     |
    +==============+=======================================================+
    | Notes        | This is ID #18 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Reproducibility, Provenance                 |
    +--------------+-------------------------------------------------------+

52 Reproducibility of data products
-----------------------------------

Jama Connect entry: `DUNE STKH #122 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15294>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support the reproduction of data  |
    |              | products from the provenance stored in the output.    |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Reproducibility, Provenance                           |
    +--------------+-------------------------------------------------------+

52.1 Reproducibility with pseudo-random numbers
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #36 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14596>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall provide a facility to produce     |
    |              | random numbers enabling algorithms to create          |
    |              | reproducible data in concurrent contexts.             |
    +==============+=======================================================+
    | Notes        | This is ID #22 from the original DUNE document.       |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Original, Reproducibility, Provenance                 |
    +--------------+-------------------------------------------------------+

52.2 Independence from unique hardware characteristics
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #63 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=14632>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall operate independently of unique   |
    |              | characteristics of existing hardware.                 |
    +==============+=======================================================+
    | Notes        | This is ID #62 as proposed to DUNE.                   |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Reproducibility, Provenance                           |
    +--------------+-------------------------------------------------------+

53 Command line interface (CLI)
-------------------------------

Jama Connect entry: `DUNE STKH #125 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15710>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall provide a command-line interface  |
    |              | that allows the setting of configuration parameters.  |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Configuration                                         |
    +--------------+-------------------------------------------------------+

54 Support local configuration changes
--------------------------------------

Jama Connect entry: `DUNE STKH #126 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15715>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support the use of local          |
    |              | configuration changes with respect to a separate      |
    |              | complete configuration to modify the execution of a   |
    |              | program.                                              |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Configuration                                         |
    +--------------+-------------------------------------------------------+

55 Configuration tracing
------------------------

Jama Connect entry: `DUNE STKH #127 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15718>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework configuration system shall have an      |
    |              | option to provide diagnostic information for an       |
    |              | evaluated configuration, including origins of final   |
    |              | parameter values.                                     |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Configuration                                         |
    +--------------+-------------------------------------------------------+

56 Configuration language single point of maintenance
-----------------------------------------------------

Jama Connect entry: `DUNE STKH #128 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15723>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The language used for configuring a framework program |
    |              | shall include features for maintaining hierarchical   |
    |              | configurations from a single point of maintenance.    |
    +==============+=======================================================+
    | Notes        | This must be met by each configuration language.      |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Configuration                                         |
    +--------------+-------------------------------------------------------+

57 Enable identification of data sets containing chunked data products
----------------------------------------------------------------------

Jama Connect entry: `DUNE STKH #129 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15737>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall record metadata identifying data  |
    |              | sets where the framework took special measures to     |
    |              | process data collections of unconstrained size.       |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Provenance, Chunkification                            |
    +--------------+-------------------------------------------------------+

58 Thread-safe design for algorithms
------------------------------------

| Jama Connect entry: `DUNE STKH #130 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15742>`__
| See :ref:`programming_paradigm:Functional programming`

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall facilitate the development of     |
    |              | thread-safe algorithms.                               |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Concurrency and multithreading                        |
    +--------------+-------------------------------------------------------+

59 Framework build flags
------------------------

Jama Connect entry: `DUNE STKH #131 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15744>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework build system shall support options that |
    |              | enable debugging executed code.                       |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Debugging                                             |
    +--------------+-------------------------------------------------------+

60 Floating-point environment
-----------------------------

Jama Connect entry: `DUNE STKH #132 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15746>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall allow the per-execution setting   |
    |              | of the float-point environment to control the         |
    |              | handling of IEEE floating-point exceptions.           |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Reproducibility, Error handling, Debugging            |
    +--------------+-------------------------------------------------------+

61 Composing configurations of framework components
---------------------------------------------------

Jama Connect entry: `DUNE STKH #133 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15775>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall support executing programs        |
    |              | configured by composing configurations of separate    |
    |              | components.                                           |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Configuration                                         |
    +--------------+-------------------------------------------------------+

62 Graceful shutdown of framework program
-----------------------------------------

Jama Connect entry: `DUNE STKH #134 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15787>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall attempt a graceful shutdown by    |
    |              | default.                                              |
    +==============+=======================================================+
    | Notes        | A *graceful shutdown* refers to a framework program   |
    |              | that completes the processing of all in-flight data,  |
    |              | safely closes all open input and output files, cleans |
    |              | up connections to external entities (e.g. databases), |
    |              | etc. before the program ends.  This ensures that no   |
    |              | resources are left in ill-defined states and that all |
    |              | output files are readable and valid.                  |
    |              |                                                       |
    |              | An important example of this is when a batch job      |
    |              | exceeds a time limit and the grid system sends a      |
    |              | signal to shutdown the job, which should end          |
    |              | gracefully.                                           |
    +--------------+-------------------------------------------------------+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Error handling                                        |
    +--------------+-------------------------------------------------------+

62.1 Graceful shutdown for uncaught exception
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #135 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15788>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall by default attempt a graceful     |
    |              | shutdown upon receiving an uncaught exception from    |
    |              | user algorithms.                                      |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Error handling                                        |
    +--------------+-------------------------------------------------------+

62.2 Graceful shutdown for received signal
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Jama Connect entry: `DUNE STKH #136 <https://fnal-prod.jamacloud.com/perspective.req?projectId=63&docId=15789>`__

.. todo:: Not yet referenced in design

.. table::
    :widths: 15 85

    +--------------+-------------------------------------------------------+
    | Requirement  | The framework shall by default attempt a graceful     |
    |              | shutdown when receiving a signal.                     |
    +==============+=======================================================+
    | Status       | Approved                                              |
    +--------------+-------------------------------------------------------+
    | Tags         | Error handling                                        |
    +--------------+-------------------------------------------------------+
