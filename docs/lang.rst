YamSql Lang
===========

.. _confd:

Config Load Directory
---------------------



.. _Frontmatter:

Frontmatter
-----------

.. _List:

List
----

Yaml List

.. _SqlName:

SqlName
-------

SqlNames defined a SQL identifier. The colon is a special symbol.

.. _SqlType:

SqlType
-------

The following characters prevent processing of the string:

- ``"`` double quotes
- ``%`` percent sign
- ``( … )`` pair of parenthesis

as does the occurence of no period (``.``).

Examples of the proccessing algorithm

.. code-block:: plpgsql

 varchar     -> varchar
 a.b         -> "a"."b"
 "a".b       -> "a".b
 "a.b"       -> "a.b"
 a.b(10)     -> a.b(10)
 a.b%ROWTYPE -> a.b%ROWTYPE

.. _String:

String
------

Strings are Yaml strings. In most cases they can be assigned without special care:

.. code-block:: yaml

 # test
 key: this is a string.

But there are some special cases, where things go wrong.

1. Inputs like ``true`` or ``false`` are interpreted as :ref:`Bool` and have to be en-quoted.
2. Quotes are used to mark strings. If you need the string ``"default value"``, you can use ``"""default value"""``. 

.. _Bool:

Bool
----

Bools are Yaml boolean values. Values can be ``true`` or ``false`` 

