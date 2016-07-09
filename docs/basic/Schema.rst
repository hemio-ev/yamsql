.. _Schema:

Schema
======

A _schema_ consists of a folder named with the schema name (given via the _schema_ option in [schema.yml](#schemayaml)). It must contain at least the following structure.
```
schema.yml
```
The parts are described in detail via the respective articles listet below.

* :ref:`Domains`
* :ref:`Functions`
* :ref:`Tables`
* :ref:`Triggers`
* :ref:`Types`

In the database each schema is represented via a SCHEMA with the schemas name.

schema.yml
----------

*name* :ref:`SqlName`
 Must coincide with the folder name

*description* :ref:`String`
 What the schema is for

dependencies :ref:`List` [:ref:`SqlName`]
 Schemas which are required to be loaded for this schema to work

Example:

.. code-block:: yaml

 name: email
 description: E-Mail System
 dependencies:
  - domains
 x: true
 y: 1

.. code-block:: yaml

 name: email
 x: "a"
 description: |
  Email and Mailing lists
 
  This module sends the following signals:
   - email/alias
   - email/list
   - email/mailbox
   - email/redirection
 
 dependencies:
  - dns
 
 priv_all_all:
  - system
 priv_usage:
  - userlogin
  - backend
 
 exec_post_install: |
  SELECT system._setup_register_service('email', 'email');
  SELECT system._setup_register_subservice('email', 'mailbox');
  SELECT system._setup_register_subservice('email', 'alias');
  SELECT system._setup_register_subservice('email', 'redirection');
  SELECT system._setup_register_subservice('email', 'list');
  SELECT system._setup_register_subservice('email', 'dns_activatable');
  SELECT setval('email.mailbox_uid_seq', 100000);
 
 function_templates:
  -
   template: insert
   description: does the contingent checks
   variables:
    -
     name: v_num_total
     type: int
    -
     name: v_num_domain
     type: int
   body_prelude: |
     PERFORM email._address_valid(p_localpart, p_domain);
 
     v_num_total := (SELECT COUNT(*) FROM email._address() AS t WHERE t.owner=v_owner AND t.subservice=v_subservice);
     v_num_domain := (SELECT COUNT(*) FROM email._address() AS t WHERE t.owner=v_owner AND t.subservice=v_subservice AND t.domain = p_domain);
 
     PERFORM system._contingent_ensure(
         p_owner:=v_owner,
         p_domain:=p_domain,
         p_service:='email',
         p_subservice:=v_subservice,
         p_current_quantity_total:=v_num_total,
         p_current_quantity_domain:=v_num_domain);
