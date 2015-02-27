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
