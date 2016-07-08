Domains
=======

- <http://www.postgresql.org/docs/9.3/interactive/sql-createdomain.html>

# `domains/`
Domains are basically semantic aliases for build in types with some extra constraints (checks).

Example:
```YAML
name: email_address
description: Valid e-mail address
type: varying(254)

checks:
 -
  name: email_regex
  description: Ensures that the address contains an @ and something before the @
  check: POSITION('@' IN VALUE) > 1
```

