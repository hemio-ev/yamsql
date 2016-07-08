.. _Role:

Role
====

Roles are a unification of the concept of users an groups.

* **name**        (:ref:`SqlName`): role name
* **description** (:ref:`String`): description
* login       (:ref:`Bool`): can role login, non-login roles are groups (default: _false_)
* password    (:ref:`String`): password in plain text
* member_in    (list of :ref:`SqlName`\ s): list of roles the role is member of
