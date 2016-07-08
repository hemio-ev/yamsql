.. _Function:

Function
========

All files directly contained in *<module-dir>/functions.d/* and ending with `.sql` are regarded as function defintions for the module.

More informations
* <http://www.postgresql.org/docs/9.4/static/sql-createfunction.html>
* <http://www.postgresql.org/docs/9.4/static/sql-alterfunction.html>

All required options are marked with **bold** font weight.

- **name** (:ref:`SqlName`): function name
- **description** (:ref:`String`): what the function is good for
- **returns** (:ref:`SqlType`): return type of the function, the value *TABLE* is special (see return_table)
- *parameters* (list of :ref:`Variable`\ s): parameters the function takes
- *templates* (list of :ref:`SqlName`\ s): list of template names, from which this function derives definitions (see :ref:`FunctionTpl`)
- *returns_columns* (list of :ref:`Parameter`\ s): if the value of *return* is TABLE (case sensitive), this options defines the columns that are returned
- *priv_execute* (list of :ref:`SqlName`\ s): Role that has the privilege to execute the function
- *security_definer* (:ref:`Bool`): If true, the function is executed with the privileges of the owner! Owner has to be given, if this is true (not implemented yet!)
- *owner* (:ref:`SqlName`): owner of the function
- *language* (:ref:`String`): language in which the body is written.
- *variables* (list of :ref:`Variable`\ s)
- **body** (:ref:`String`): the code of the function (body)

