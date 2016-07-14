Language Constructs
===================

Files
+++++

.. _confd:

Config Load Directory
---------------------

Only files ending with an alphanumeric character and not beginning with a dot
are considered.

.. _Frontmatter:

Front Matter
------------

YAML front matter is a method to add YAML content to a document `originally defined by Jekyll <http://jekyllrb.com/docs/frontmatter/>`_. The YAML part is 
added to the beginning of the document between triple-dashed lines.

.. code-block:: html
 :caption: General structure of a document with YAML front matter
 
 ---
 <YAML>
 ---
 <CONTENT>

Value Types
+++++++++++

.. _List:

List
----

Lists are just YAML Lists

.. code-block:: yaml
 :caption: Different ways for providing lists

 # recommended
 list1:
  - this
  - is a
  - list
 dlist1:
  -
   a: list with
   b: sub structure
  # this variant saves a line
  - a: x
    b: y
    
 # mostly discured for YamSql
 list2: [this, is a, list]
 dlist2: [{a: list with, b: sub structure}, {a: x, b: y}]

.. _SqlName:

SQL Identifier
--------------

Internally, if no double quote character is present, the parts seperated by periods are escaped or enquoded. If a double quote character is present, it is
assumed that the identifier is properly enquoted.

.. _SqlType:

SQL Type
--------

The following characters prevent processing of the string:

- ``"`` double quotes
- ``%`` percent sign
- ``( … )`` pair of parenthesis

as does the occurence of no period (``.``).

.. code-block:: plpgsql
 :caption: Examples of the proccessing algorithm

 varchar     -> varchar
 a.b         -> "a"."b"
 "a".b       -> "a".b
 "a.b"       -> "a.b"
 a.b(10)     -> a.b(10)
 a.b%ROWTYPE -> a.b%ROWTYPE

.. _String:

String
------

Strings are YAML strings. In most cases they can be given unquoted. However, there are some special cases, where things go wrong.

1. Inputs like ``true`` or ``false`` are interpreted as :ref:`Bool` and have to be en-quoted.
2. Quotes are used to mark strings. If you need the string ``"string"``, you can use ``"""string"""``. 

.. code-block:: yaml

 key1a: this is a string.
 # also possible but not required
 key1b: "this is a string."
 # this one needs quoting
 key2: "true"
 # this represents the string "string"
 key3: """string"""

.. _Bool:

Bool
----

Bools are Yaml boolean values. Values can be ``true`` or ``false`` 

