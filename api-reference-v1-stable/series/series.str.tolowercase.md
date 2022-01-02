---
description: Converts all characters to lower case.
---

# Series.str.toLowerCase

> danfo.Series.str.toLowerCase(options)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L20)]

| Parameters | Type   | Description                                                     | Default                                                |
| ---------- | ------ | --------------------------------------------------------------- | ------------------------------------------------------ |
| options    | Object | **inplace**: Whether to perform the operation in-place or not.  | <p>{</p><p><strong>inplace</strong>: false</p><p>}</p> |

**Example**

Convert all characters in each string element to small letter

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['LOWER BOY', 'CAPITALS', 'SENTENCE', 'SWAPCASE']
let sf = new dfd.Series(data)
sf.str.toLowerCase().print()
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
║ 0 │ lower boy            ║
╟───┼──────────────────────╢
║ 1 │ capitals             ║
╟───┼──────────────────────╢
║ 2 │ sentence             ║
╟───┼──────────────────────╢
║ 3 │ swapcase             ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
