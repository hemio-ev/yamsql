.. _Sequence:

Sequence
========

Sequences

The :ref:`confd` is :file:`sequences.d` and must contain files with the following
strucutre.

*name* :ref:`SqlName`
 Name

*description* :ref:`String`
 Description

increment :ref:`Integer`
 Default 1

min_value :ref:`Integer`
 Minimum value

max_value :ref:`Integer`
 Maximum value

start_value :ref:`Integer`
 Start value

cache :ref:`Integer`
 Numer of values to prealloc

cycle :ref:`Bool`
 Cycle

owned_by_column :ref:`SqlName`  
 Owned by column
