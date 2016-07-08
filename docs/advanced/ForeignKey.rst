.. _ForeignKey:

FK
==

- **name** (:ref:`SqlName`): Just a name
- **columns** (list of [SqlName`\ s): Columns in this table
- **ref_table** (:ref:`SqlName`): Table to reference
- **ref_columns**  (list of :ref:`SqlName`\ s): Columns in referenced table (order must match the one in *columns*)
- on_delete (:ref:`String`): Action when entry in foreign table is deleted
- on_update (:ref:`String`): Action when entry in foreign table is update
