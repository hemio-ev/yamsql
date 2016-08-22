.. _Trigger:

Trigger
=======

The :ref:`confd` is :file:`triggers.d`.

*name* :ref:`SqlName`
 Name

*tables* :ref:`List` [:ref:`SqlName`]
 Tables

*moment* :ref:`String`
 The moment at which the trigger is fired. Possible values are
  
  - ``BEFORE``
  - ``AFTER``
  - ``INSTEAD OF``

*events* :ref:`List` [:ref:`String`]
 Events at which the trigger is fired.
 
  - ``INSERT``
  - ``UPDATE [ OF column_name [, ... ] ]``
  - ``DELETE``

for_each
 Fire trigger for each
 
  - ``ROW``
  - ``STATEMENT``

condition :ref:`String`
 When condition that has to be fullfilled for the trigger to be fired.

language :ref:`String`
 See :ref:`Function (language) <Function-language>`

language :ref:`String`
 See :ref:`Function (variables) <Function-variables>`

body :ref:`String`
 See :ref:`Function (body) <Function-body>`

External Resources
------------------

- `PostgreSQL's CREATE TRIGGER statement <https://www.postgresql.org/docs/current/static/sql-createtrigger.html>`_
