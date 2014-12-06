All files directly contained in *<module-dir>/tables.d/* and ending with `.yamsql` are regarded as table defintions for the module.

* <http://www.postgresql.org/docs/9.4/static/sql-createtable.html>
* <http://www.postgresql.org/docs/9.4/static/sql-altertable.html>

*   **name**         ([[SqlName]]): table name
*   **description**  ([[String]]): what this table is good for
*   **columns**      (list of [[Column]]s): columns contained in this table
*   **primaryKey**   (list of [[SqlName]]): list of column names that define the primary key
*   foreignKeys   (list of [[ForeignKey]]s): constains values via foreign keys
*   checks        (list of [[Check]]s): validity checks applied to the table
*   inherits      (list of [[SqlName]]s): 
*   privSelect    (list of [[SqlName]]s): grant SELECT to given roles for this table
*   privInsert    (list of [[SqlName]]s): grant INSERT
*   privUpdate    (list of [[SqlName]]s): grant UPDATE
*   privDelete    (list of [[SqlName]]s): grant DELETE
*   templates     (list of [[SqlName]]s): (see [[TableTpl]])