All files directly contained in *<module-dir>/tables.d/* and ending with `.yamsql` are regarded as table defintions for the module.

* <http://www.postgresql.org/docs/9.4/static/sql-createtable.html>
* <http://www.postgresql.org/docs/9.4/static/sql-altertable.html>

Structure

*   **name**         ([[SqlName]]): table name
*   **description**  ([[String]]): what this table is good for
*   **columns**      (list of [[Column]]s): columns contained in this table
*   **primary_key**   (list of [[SqlName]]): list of column names that define the primary key
*   foreign_keys   (list of [[ForeignKey]]s): constains values via foreign keys
*   checks        (list of [[Check]]s): validity checks applied to the table
*   inherits      (list of [[SqlName]]s): 
*   priv_select    (list of [[SqlName]]s): grant SELECT to given roles for this table
*   priv_insert    (list of [[SqlName]]s): grant INSERT
*   priv_update    (list of [[SqlName]]s): grant UPDATE
*   priv_delete    (list of [[SqlName]]s): grant DELETE
*   templates     (list of [[SqlName]]s): (see [[TableTpl]])
