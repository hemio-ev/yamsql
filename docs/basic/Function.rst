.. _Function:

Function
========

The :ref:`confd` is :file:`functions.d`. For functions two allowed formats for giving the functions body exist. The usual variant is to give the following YAML structure including the ``body`` value. The second variant is to give the following YAML structure as :ref:`Frontmatter` (i. e. fenced with ``---`` lines) providing the body as content following the frontmatter. The Examples_ include both variants.

The recommended practice is to use the :ref:`Frontmatter` style while using a
filename extension that matches the used language (``.pgsql``, ``.sql``, ``.py``)
to enable syntax highlighting in editors.

*name* :ref:`SqlName`
 Function name
 
*description* :ref:`String` 
 Function description

*returns* :ref:`SqlType`
 Return type of the function, the value *TABLE* is special (see return_table)

parameters :ref:`List` [:ref:`Variable`]
 parameters the function takes

templates :ref:`List` [:ref:`SqlName`]
 list of template names, from which this function derives definitions (see :ref:`FunctionTpl`)

returns_columns :ref:`List` [:ref:`Parameter`]
 If the value of *return* is ``TABLE`` (case sensitive), this options defines the columns that are returned

priv_execute :ref:`List` [:ref:`SqlName`]
 Role that has the privilege to execute the function

security_definer :ref:`Bool`
 If true, the function is executed with the privileges of the owner! Owner has to be given, if this is true

owner :ref:`SqlName`
 owner of the function

language :ref:`String`:
 language in which the body is written.

variables :ref:`List` [:ref:`Variable`]
 Variables
 
body :ref:`String`
 The code of the function (body)

.. _Parameter:

Parameter
---------

*name* :ref:`SqlName`
 Name

*type* :ref:`SqlType`
 Type

description :ref:`String`
 Description

.. _Variable:

Variable
--------

*name* :ref:`SqlName`
 Name

*type* :ref:`SqlType`
 Type

description :ref:`String`
 Description

default :ref:`String`
 Default

Examples
--------

.. code-block:: yaml
 :caption: Usual definition using plain YAML

 name: f
 description: |
  Always returns ``1``
 returns: int
 body: |
 
  RETURN 1;

.. code-block:: plpgsql
 :caption: Same function with the function body following a :ref:`Frontmatter`

 ---
 name: f
 description: |
  Always returns ``1``
 returns: int
 ---
 
 RETURN 1;

.. code-block:: py
 :caption: Same function written in Python 3

 ---
 name: f
 description: |
  Always returns ``1``
 returns: int
 language: plpython3u
 ---
 
 return 1

External Resources
------------------

* `PostgreSQL's CREATE FUNCTION statement <http://www.postgresql.org/docs/current/static/sql-createfunction.html>`_

