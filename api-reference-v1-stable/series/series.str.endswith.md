---
description: Checks whether a string ends with specified characters
---

# Series.str.endsWith

> danfo.Series.str.**endsWith**(str, options)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L133)]

| Parameters | Type   | Description                                                     | Default                                                |
| ---------- | ------ | --------------------------------------------------------------- | ------------------------------------------------------ |
| str        | string | the character(s) to check                                       | ""                                                     |
| options    | Object | **inplace**: Whether to perform the operation in-place or not.  | <p>{</p><p><strong>inplace</strong>: false</p><p>}</p> |

**Returns**: Series (Boolean element)

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower', 'CAPITALS', 'this is a sentence', 'SwApCaSe']
let sf = new dfd.Series(data)
sf.str.endsWith("e").print()
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
║ 1 │ false                ║
╟───┼──────────────────────╢
║ 2 │ true                 ║
╟───┼──────────────────────╢
║ 3 │ true                 ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
