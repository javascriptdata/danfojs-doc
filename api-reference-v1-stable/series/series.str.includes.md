---
description: Checks whether a string contains the specified string/characters
---

# Series.str.includes

> danfo.Series.str.includes(str, options)  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L147)]

| Parameters | Type   | Description                                                     | Default                                                |
| ---------- | ------ | --------------------------------------------------------------- | ------------------------------------------------------ |
| str        | string | the character(s) to check                                       | ""                                                     |
| options    | Object | **inplace**: Whether to perform the operation in-place or not.  | <p>{</p><p><strong>inplace</strong>: false</p><p>}</p> |

**Returns**: Series (boolean element)

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower', 'CAPITALS', 'this is a sentence', 'SwApCaSe']
let sf = new dfd.Series(data)
sf.str.includes("C").print()
```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ false                ║
╟───┼──────────────────────╢
║ 1 │ true                 ║
╟───┼──────────────────────╢
║ 2 │ false                ║
╟───┼──────────────────────╢
║ 3 │ true                 ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
