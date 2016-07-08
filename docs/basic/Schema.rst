.. _Schema:

Schema
======

A _schema_ consists of a folder named with the schema name (given via the _schema_ option in [schema.yml](#schemayaml)). It must contain at least the following structure.
```
schema.yml
```
The parts are described in detail via the respective articles listet below.

* :ref:`Domains`
* :ref:`Functions`
* :ref:`Tables`
* :ref:`Triggers`
* :ref:`Types`

In the database each schema is represented via a SCHEMA with the schemas name.

schema.yml
----------

name :ref:`SqlName`
 Must coincide with the folder name

description :ref:`String`
 What the schema is for

dependencies :ref:`List` [:ref:`SqlName`]
 Schemas which are required to be loaded for this schema to work

Example:

.. code-block:: yaml

 name: email
 description: E-Mail System
 dependencies:
  - domains

