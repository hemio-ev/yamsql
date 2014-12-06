All files directly contained in *<module-dir>/functions.d/* and ending with `.pgsql` are regarded as function defintions for the module.

More informations
* <http://www.postgresql.org/docs/9.4/static/sql-createfunction.html>
* <http://www.postgresql.org/docs/9.4/static/sql-alterfunction.html>

All required options are marked with **bold** font weight.

- **name** ([[SqlName]]): function name
- **description** ([[String]]): what the function is good for
- **return** ([[String]]): return type of the function, the value *TABLE* is special (see return_table)
- *parameters* (list of [[Variable]]s): parameters the function takes
- *templates* (list of [[SqlName]]s): list of templates, used for this function (see [[FunctionTpl]])
- *return_columns* (list of [[Parameter]]s): if the value of *return* is TABLE (case sensitive), this options defines the columns that are returned
- *priv_execute* (list of [[SqlName]]s): Role that has the privilege to execute the function
- *security_definer* ([[Bool]]): If true, the function is executed with the privileges of the owner! Owner has to be given, if this is true (not implemented yet!)
- *owner* ([[SqlName]]): owner of the function
- *language* ([[String]]): language in which the body is written.
- **body** ([[String]]): the code of the function (body)

