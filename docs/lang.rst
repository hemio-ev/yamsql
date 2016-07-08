YamSql Lang
===========

.. _SqlName:

SqlName
-------

SqlNames defined a SQL identifier. The colon is a special symbol.

.. _SqlType:

SqlType
-------

The following characters prevent processing of the string:
- *"* (double quotes)
- *%* (percent sign)
- *( … )* (pair of parenthesis)
as does the occurence of no period (*.*).

Examples of the proccessing algorithm
 
```
varchar -> varchar
a.b -> "a"."b"
a.b(10) -> a.b(10)
a.b%ROWTYPE -> a.b%ROWTYPE
"a".b -> "a".b
"a.b" -> "a.b"
```

.. _String:

String
------

Strings are usual *Yaml* strings. In most cases they can be assigned without special care:
> key: this is a string.

But there are some special cases, where things go wrong.
1. Inputs like *true* or *no* are interpreted as [[Bool]] and have to be en-quoted.
2. Quotes are used to mark strings. If you need the string *"default value"*, you can use *"""default value"""*. 

.. _Bool:

Bool
----

Bools are usual Yaml boolean values. Values can be ``true`` or ``false`` 

