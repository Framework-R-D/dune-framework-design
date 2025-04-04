Algorithms
==========

As :ref:`mentioned earlier <programming_paradigm:Higher-order functions supported by Phlex>`, an algorithm is registered with the framework as an operator to a higher-order function (HOF).
In general, Phlex supports the registration of C++ algorithms with function signatures like (see :ref:`below <algorithms:HOF operators>`):

.. code:: c++

   return_type function_name(P1, ..., Pn, R1, ..., Rm) [qualifiers];

where the types :cpp:`P1, ..., Pn` denote types of data products and the types :cpp:`R1, ..., Rm` indicate resources.

.. admonition:: Chris Green
   :class: admonition-chg

   Should "resources" be a term with a glossary definition?

We will first discuss the :ref:`data-product and resource types <algorithms:Input parameters>`, followed by the :ref:`return type <algorithms:Return types>`, and then the :ref:`function name and optional qualifers <algorithms:Function names and qualifiers>`.

Input parameters
----------------

A data product of type :cpp:`P` may be presented to a C++ algorithm if the corresponding input parameter (i.e. the relevant :cpp:`P1, ..., PN` type) is one of the following:

- :cpp:`P const&` — read-only access to a data product provided through a reference
- :cpp:`P const*` — read-only access to a data product provided through a pointer
- :cpp:`P` — the data product is copied into an object (assumes data product is copyable) [#f1]_
- :cpp:`phlex::handle<P>` — a lightweight object that provides read-only access to a data product as well as any metadata associated with it

For each of these cases, the data product itself remains immutable.

Whereas data products may to be copied, resources of type :cpp:`R` may not.
The following types are therefore supported:

- :cpp:`R const&` — read-only access to a resource provided through a reference
- :cpp:`R const*` — read-only access to a resource provided through a pointer

Resources are described in more detail :ref:`here <resources:Resources>`.

Return types
------------

The meaning of an algorithm's return type depends on the HOF and is discussed in the :ref:`section on HOF operators <algorithms:HOF operators>`.
However, to simplify the discussion we introduce to concept of the *created data-product type*.
For Phlex to appropriately schedule the execution of algorithms and manage the lifetimes of data products, the framework itself must retain ownership of the data products.
This means that the data products created by algorithms must have types that connote unique ownership.
Such semantics are conveyed to the framework by returning *values* and not null objects.

A created data-product type supports either:

- :cpp:`T`, where :cpp:`T` is not a pointer or reference type
- :cpp:`std::unique_ptr<T>`, where the created object is non-null

The following types (or their equivalents) are forbidden as created data-product types because they do not imply unambiguous ownership:

- *bare pointer types*, such as :cpp:`T*` or :cpp:`T const*`
- *reference types*, such as :cpp:`T&` or :cpp:`T const&`

Function names and qualifiers
-----------------------------

The :cpp:`function_name` :ref:`above <algorithms:Algorithms>` may be any function name supported by the C++ language.
Code authors should aim to implement algorithms as free functions.
However, in some cases it may be necessary for class member functions to be used instead.
When member functions are required, the qualifier :cpp:`const` should be specified to indicate that the class instance remains immutable during the execution of the member function [#f2]_.

Framework registration
----------------------

.. attention::

   The C++ interface below is illustrative and not intended to reflect the final registration interface.

To the extent possible, Phlex preserves data flow among data products and algorithms.
This is indicated in the interface for registering algorithms.
In some cases, access to a limited resource is required and the algorithm signature will specify dependencies on not only the data of interest but also the shared resource.

Consider the following C++ classes and function:

.. code:: c++

   class hits { ... };
   class tracks { ... };

   tracks make_tracks(hits const& hs) { ... }

where the implementations of `hits`, `tracks`, and `make_tracks` are unspecified.
Phlex adopts a `fluent interface <https://en.wikipedia.org/wiki/Fluent_interface>`_ for registering algorithms.
This makes it possible to express the sentence:

    *With the function* `make_tracks` *and unlimited concurrency, transform "hits" to "tracks" for each spill.*

in terms of the C++ *registration stanza*:

.. code:: c++

   PHLEX_REGISTER_ALGORITHMS(m)    // <== Registration opener
   {
     m.with(                       // <-- Beginning of registration statement
            make_tracks,           // (1) Algorithm/HOF operation
            concurrency::unlimited // (2) Allowed CPU concurrency
           )
      .transform(                  // (3) Higher-order function
                 "good_hits"       // (4) Spec. of input data product to make_tracks
                )
      .to("good_tracks")           // (5) Spec. of output data product from make_tracks
      .for_each("spill")           // (6) Scope of input/output data products
      ;                            // <-- End of registration statement
   }

The registration stanza is included in C++ file called a :term:`module`, which is a compiled library that is dynamically loadable by Phlex.

.. admonition:: Chris Green
   :class: admonition-chg

   Do you mean a C++ module, or a linker-defined module? It seems a bit strange to describe a, "C++ file" as a "compiled library ..."

The stanza is introduced by an *opener*—e.g. :cpp:`PHLEX_REGISTER_ALGORITHMS(m)`—followed by a *registration block*, a block of code between two curly braces that contains one or more *registration statements*.
A registration statement contains a series of chained *clauses*, starting with a :cpp:`with(...)` clause.

.. admonition:: Chris Green
   :class: admonition-chg

   What significance does the ordering have beyond the first :cpp:`with(...)` or :cpp:`make(...)`?
   Is this enforced?
   If so, is this at compile time, configuration time or run time?

In the case of a transform, six pieces of information are provided in the registration statement:

1. The algorithm/HOF operator to be used
2. The maximum number of CPU threads the framework can use when invoking the algorithm :dune:`24.2 Specification of algorithm's maximum number of CPU threads`
3. The HOF to be used (generally expressed as an active verb)

   .. admonition:: Chris Green
      :class: admonition-chg

      I think I know what is meant here, but could we make it a little clearer, e.g. "The name of the HOF to be used, which generally should be expressed as an action, e.g. ``make_tracks`` or ``calculate_de_dx``?"

4. The product specification(s) from which to form the input data product sequence :dune:`28 Specification of data products required by an algorithm`
5. The specification(s) of the data product(s) created by the algorithm :dune:`29 Specification of data products created by an algorithm`
6. The data category where the input data products are found and the output data products are to be placed

The set of information required by the framework for registering an algorithm largely depends on the HOF being used (see the :ref:`section on HOF operators <algorithms:HOF operators>` for specific interface).
However, in general, the registration code will specify which data products are required/produced by the algorithm :dune:`1.1 Algorithm Communication Via Data Products` and the hardware resources required by the algorithm :dune:`4 Algorithm hardware requirements`.
Note that the input and output data-product specifications are matched with the corresponding types of the registered algorithm's function signature.
In other words:

- :cpp:`"good_hits"` specifies a data product whose C++ type is that of the first (and, in this case, only) input parameter to :cpp:`make_tracks` (i.e. :cpp:`hits`).
- :cpp:`"good_tracks"` specifies a data product whose C++ type is the :cpp:`tracks` return type of :cpp:`make_tracks`.

When executed, the above code creates a :term:`configured higher-order function <Configured higher-order function (CHOF)>`, which serves as a node in the function-centric data-flow graph.

The registration block may contain any code supported by C++.
The block, however, must contain a registration statement to execute an algorithm.

.. important::

   A module must contain only one registration stanza.
   Note that multiple registration statements may be made in each stanza.

Accessing configuration information
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Instead of hard-coding all pieces of registration information, it is desirable to specify a subset of such information through a program's run-time configuration.
To do this, an extra argument (e.g. :cpp:`config`) is passed to the registration opener:

.. code:: c++

   PHLEX_REGISTER_ALGORITHMS(m, config)
   {
     // Get data scope from configuration, defaulting to "spill" if no data scope
     // is specified in the configuration.
     auto selected_data_scope = config.get<std::string>("data_scope", "spill");

     m.with(make_tracks, concurrency::unlimited)
      .transform("good_hits")
      .to("good_tracks")
      .for_each(selected_data_scope);
   }

.. important::

   The :cpp:`config` C++ object provides access to the configuration parameters corresponding **only to the module containing the registration stanza.**
   In other words, one registration stanza may not access the configuration parameters of another registration stanza.

   .. admonition:: Chris Green
      :class: admonition-chg

      Should we provide some limited access to framework configuration of interest (e.g. via an optional supplemental argument), such as global verbosity and/or debug flags?


Except for the specification of :cpp:`make_tracks` as the algorithm to be invoked, and :cpp:`transform` as the HOF, all other pieces of information may be provided through the configuration.

.. admonition:: Chris Green
   :class: admonition-chg

   What about :cpp:`for_each()`? Would it be simpler to list only :cpp:`make_tracks` and "C++ operations on the :cpp:m object" as exceptions?

Framework dependence in registration code
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Usually, classes like :cpp:`hits` and :cpp:`tracks` and algorithms like :cpp:`make_tracks` do not need to depend on framework interface :dune:`20 Algorithms independent of framework interface`.
There may be scenarios, however, where dependence on framework interface is required, especially if framework-specific metadata types are used by the algorithm.
In such cases, it is strongly encouraged to keep framework dependence within the module itself and, more specifically, within the registration stanza.
This can be often achieved by registering closure objects that are generated by lambda expressions.

For example, suppose a physicist would like to create an algorithm :cpp:`make_tracks_debug` that reports a spill number when making tracks.
By specifying a lambda expression that takes a :cpp:`phlex::handle<hits>` object, the data product can be passed to the :cpp:`make_tracks_debug` function, along with the spill number from the metadata accessed from the handle:

.. code:: c++

   tracks make_tracks_debug(hits const& hs, std::size_t spill_number) { ... }

   PHLEX_REGISTER_ALGORITHMS(m)
   {
     m.with([](phlex::handle<hits> hs) {
              return make_tracks_debug(*hs, hs.id()->number());
            },
            concurrency::unlimited)
      .transform("good_hits")
      .to("good_tracks")
      .for_each("spill");
   }

The lambda expression *does* depend on framework interface; the :cpp:`make_tracks_debug` function, however, retains its framework independence.

Member functions of classes
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code:: c++

   class track_maker {
   public:
     track_maker(std::size_t track_seed);
     tracks make(hits const& hs) const;
     ...
   };

   PHLEX_REGISTER_ALGORITHMS(m, config)
   {
     auto track_seed = config.get<std::size_t>("track_seed");
     auto selected_data_scope = config.get<std::string>("data_scope", "spill");

     m.make<track_maker>(track_seed)
      .with(&track_maker::make, concurrency::unlimited)
      .transform("good_hits")
      .to("good_tracks")
      .for_each(selected_data_scope);
   }

Overloaded functions
^^^^^^^^^^^^^^^^^^^^

Phlex performs a substantial amount of type deduction through the :cpp:`with(...)` clause.
This works well except in cases where the registered algorithms are overloaded functions.
For example, suppose one wants to register C++'s overloaded :cpp:`std::sqrt(...)` function with the framework.
Simply specifying :cpp:`with(std::sqrt)` will fail at compile time as the compiler will not be able to determine which overload is desired.

Instead, the code author can use the following [#f3]_:

.. code:: c++

   m.with([](double x){ return std::sqrt(x); }) ... ;

where the desired overload is selected based on the :cpp:`double` argument to the lambda expression.

.. include:: hof_operators.rst

.. rubric:: Footnotes

.. [#f1] In C++, the function signature corresponds to the function *declaration*, for which the type :cpp:`P` and :cpp:`P const` are treated identically by the compiler.
         However, for the function implementation or *definition*, algorithm authors are encouraged to use :cpp:`P const` to help guarantee the immutability of data.

         .. admonition:: Chris Green
            :class: admonition-chg

            Should this have a reference to an explanation of this at e.g. ``cppreference.com``?

.. [#f2] Phlex permits the registration of member functions that do not use the :cpp:`const` qualifier.
         However, using such functions is highly discouraged as it indicates a class instance is modifiable during member-function execution, which is at odds with Phlex's functional-programming paradigm, and DUNE's stated desire for re[rpducibility.
.. [#f3] Equivalently, one can cast :cpp:`std::sqrt` to the desired overload by using the obscure syntax :cpp:`m.with(static_cast<double(*)(double)>(std::sqrt)) ... ;` .
