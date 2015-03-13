* **name**          ([[SqlName]]): column name
* **_type_**          ([[SqlType]]): column type (see also [[Type]], [[Domain]])
* **_description_**   ([[String]]): description
* template      ([[SqlName]]): if a [[ColumnTpl]] is used, _type_ and _description_ can be omitted
* default       ([[String]]): default value (sql code)
* null          ([[Bool]]): Sql _NULL_ is allowed as value (default _false_)
* references    ([[SqlName]]): 
* on_ref_delete   ([[String]]): 
* on_ref_update   ([[String]]): 
* unique        ([[Bool]]): 
* checks        (list of [[Check]]s): 