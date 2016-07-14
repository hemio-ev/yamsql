.. _Schema:

Schema
======

A database can contain several *schemas* where each schema can contain objects like tables and functions potentially with identical names without conflicting. Thus, schemas share similarities with the concept of namespaces.

YamSql schema definitions consist of a folder which shares it's name with the schema. The folder must contain a ``schema.yml`` file.

Syntax of schema.yml
--------------------

*name* :ref:`SqlName`
 Schema name.

*description* :ref:`String`
 Schema description. |RSTcontent|

dependencies :ref:`List` [:ref:`SqlName`]
 Other schemas required for this schema to work.

Examples
--------

.. code-block:: yaml

 name: my_app
 description: |
  Main strucutre for MyApp 
 
 dependencies:
  - other_app

External Resources
------------------

- `PostgreSQL Schemas <https://www.postgresql.org/docs/current/static/ddl-schemas.html>`_
- `PostgreSQL's CREATE SCHEMA statement <https://www.postgresql.org/docs/current/static/sql-createschema.html>`_

