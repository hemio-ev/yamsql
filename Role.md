Roles are a unification of the concept of users an groups.

* **name**        ([[SqlName]]): role name
* **description** ([[String]]): description
* login       ([[Bool]]): can role login, non-login roles are groups (default: _false_)
* password    ([[String]]): password in plain text
* member_in    (list of [[SqlName]]s): list of roles the role is member of