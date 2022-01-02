---
description: Converts all characters to uppercase.
---

# Series.str.toUpperCase

> danfo.Series.str.toUpperCase(options)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L33)]

| Parameters | Type   | Description                                                     | Default                                                |
| ---------- | ------ | --------------------------------------------------------------- | ------------------------------------------------------ |
| options    | Object | **inplace**: Whether to perform the operation in-place or not.  | <p>{</p><p><strong>inplace</strong>: false</p><p>}</p> |

**Returns**:  Series (String element)

**Example**

Convert all characters in each string element to capital letter

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower boy', 'CAPITALS', 'sentence', 'SwApCaSe']
let sf = new dfd.Series(data)
sf.str.toUpperCase().print()
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
║ 0 │ LOWER BOY            ║
╟───┼──────────────────────╢
║ 1 │ CAPITALS             ║
╟───┼──────────────────────╢
║ 2 │ SENTENCE             ║
╟───┼──────────────────────╢
║ 3 │ SWAPCASE             ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
