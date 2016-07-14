.. _Type:

Type
====

Composite Type

*name* :ref:`SqlName`
 Type Name

*description* :ref:`String`
 Description

*elements* :ref:`List` [:ref:`TypeElement`] 
 TypeElements

.. _TypeElement:

Type Element
------------

*name* :ref:`SqlName`
 Name

*type* :ref:`SqlType`
 Type
 
Examples
--------

.. code-block:: yaml

    name: plant
    description: |
     Stores numbers of ``flowers`` and ``leaves`` of a plant.
    elements:
     -
      name: flowers
      type: integer
     -
      name: leaves
      type: integer

External Resources
------------------

- `PostgreSQL's CREATE TYPE statement <http://www.postgresql.org/docs/9.3/interactive/sql-createtype.html>`_
