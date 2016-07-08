.. _Column:

Column
======

* **name**          (:ref:`SqlName`): column name
* **_type_**          (:ref:`SqlType`): column type (see also :ref:`Type`, :ref:`Domain`)
* **_description_**   (:ref:`String`): description
* template      (:ref:`SqlName`): if a :ref:`ColumnTpl` is used, _type_ and _description_ can be omitted
* default       (:ref:`String`): default value (sql code)
* null          (:ref:`Bool`): Sql _NULL_ is allowed as value (default _false_)
* references    (:ref:`SqlName`): 
* on_ref_delete   (:ref:`String`): 
* on_ref_update   (:ref:`String`): 
* unique        (:ref:`Bool`): 
* checks        (list of :ref:`Check`\ s): 
