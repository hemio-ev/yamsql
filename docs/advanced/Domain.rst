.. _Domain:

Domain
======

Domains are basically semantic aliases for build in types with some extra constraints called :ref:`Checks <Check>`.

The :ref:`confd` is :file:`domains.d` and must contain files with the following
strucutre.

*name* :ref:`SqlName`
 Name
 
*description* :ref:`String`
 Description

*type* :ref:`SqlType`
 Type

default :ref:`String`
 Default

checks :ref:`List` [:ref:`Check`]
 Checks

Examples
--------

.. code-block:: yaml

    name: email_address
    description: Valid email address
    type: varying(254)

    checks:
     -
      name: email_regex
      description: |
       Ensures that the address contains an ``@`` and something before the ``@``
      check: |
       POSITION('@' IN VALUE) > 1

External Resources
------------------

- `PostgreSQL's CREATE DOMAIN statement <http://www.postgresql.org/docs/current/static/sql-createdomain.html>`_

