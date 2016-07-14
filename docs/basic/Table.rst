.. _Table:

Table
=====

The :ref:`confd` is :file:`tables.d` and must contain files with the following
strucutre.

*name*         :ref:`SqlName`
 table name

*description*  :ref:`String`
 what this table is good for

*columns*      :ref:`List` [:ref:`Column`]
 columns contained in this table

*primary_key*   :ref:`List` [:ref:`SqlName`]
 list of column names that define the primary key

foreign_keys   :ref:`List` [:ref:`ForeignKey`]
 constains values via foreign keys

checks        :ref:`List` [:ref:`Check`]
 validity checks applied to the table

inherits      (:ref:`List` [:ref:`SqlName`]
 Inherits

priv_select    :ref:`List` [:ref:`SqlName`]
 grant SELECT to given roles for this table

priv_insert    :ref:`List` [:ref:`SqlName`]
 grant INSERT

priv_update    :ref:`List` [:ref:`SqlName`]
 grant UPDATE

priv_delete    :ref:`List` [:ref:`SqlName`]
 grant DELETE

templates     :ref:`List` [:ref:`SqlName`]
 (see :ref:`TableTpl`)

.. _Column:

Column
------


*name*          :ref:`SqlName`
 column name

*type*          :ref:`SqlType`
 column type (see also :ref:`Type`, :ref:`Domain`)

*description*   :ref:`String`
 description

template        :ref:`SqlName`
 if a :ref:`ColumnTpl` is used, _type_ and _description_ can be omitted

default         :ref:`String`
 default value (sql code)

null            :ref:`Bool`
 Sql _NULL_ is allowed as value (default _false_)

references      :ref:`SqlName`
 References

on_ref_delete   :ref:`String`
 On Ref Delete

on_ref_update   :ref:`String`
 On Ref Update

unique          :ref:`Bool`
 Unique

checks        :ref:`List` [:ref:`Check`]
 Checks
 
.. _ForeignKey:

Foreign Key
-----------

*name* :ref:`SqlName`
 Just a name

*columns* :ref:`List` [:ref:`SqlName`]
 Columns in this table

*ref_table* :ref:`SqlName`
 Table to reference

*ref_columns*  :ref:`List` [:ref:`SqlName`]
 Columns in referenced table (order must match the one in *columns*)

on_delete :ref:`String`
 Action when entry in foreign table is deleted

on_update :ref:`String`
 Action when entry in foreign table is update


External Resources
------------------

* `PostgreSQL's CREATE TABLE statement <http://www.postgresql.org/docs/9.4/static/sql-createtable.html>`_

