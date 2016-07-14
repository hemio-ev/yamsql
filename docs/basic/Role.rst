.. _Role:

Role
====

Roles are a unification of the concept of users an groups.

*name*        :ref:`SqlName`
 Role name

*description* :ref:`String`
 Description

login       :ref:`Bool`
 Can role login, non-login roles are groups (default: *false*)

password    :ref:`String`
 password in plain text

member_in   :ref:`List` [:ref:`SqlName`]
 List of roles the role is member of

External Resources
------------------

- `PostgreSQL's CREATE ROLE <https://www.postgresql.org/docs/current/static/sql-createrole.html>`_

