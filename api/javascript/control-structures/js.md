---
layout: api-command
language: JavaScript
permalink: api/javascript/js/
command: js
io:
    -   - r
        - value
---

# Command syntax #

{% apibody %}
r.js(jsString) &rarr; value
{% endapibody %}

# Description #

Create a javascript expression.

__Example:__ Concatenate two strings using Javascript'

```js
r.js("'str1' + 'str2'").run(conn, callback)
```

__Example:__ Select all documents where the 'magazines' field is greater than 5 by running Javascript on the server.

```js
r.table('marvel').filter(
    r.js('(function (row) { return row.magazines > 5; })')
).run(conn, callback)
```


__Example:__ You may also specify a timeout in seconds (defaults to 5).

```js
r.js('while(true) {}', {timeout:1.3}).run(conn, callback)
```

