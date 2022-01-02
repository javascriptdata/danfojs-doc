---
description: the position of the first found occurrence of a specified value in a string
---

# Series.str.indexOf

> danfo.Series.str.indexOf(str, options)  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L161)]

| Parameters | Type   | Description                                                     | Default                                                |
| ---------- | ------ | --------------------------------------------------------------- | ------------------------------------------------------ |
| str        | string | the string to obtain its index                                  | ""                                                     |
| options    | Object | **inplace**: Whether to perform the operation in-place or not.  | <p>{</p><p><strong>inplace</strong>: false</p><p>}</p> |

**Returns: **Series

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower', 'CAPITALS', 'this is a sentence', 'SwApCaSe']
let sf = new dfd.Series(data)
sf.str.indexOf("C").print()
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
║ 0 │ -1                   ║
╟───┼──────────────────────╢
║ 1 │ 0                    ║
╟───┼──────────────────────╢
║ 2 │ -1                   ║
╟───┼──────────────────────╢
║ 3 │ 4                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
