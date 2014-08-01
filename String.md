*String*s are usual *Yaml* strings. In most cases they can be assigned without special care:
> key: this is a string.
But there are some special cases, where things go wrong.
1. Inputs like *true* or *no* are interpreted as [[Bool]] and have to be en-quoted.
2. Quotes are used to mark strings. If you need the string *"default value"*, you can use *"""default value"""*. 