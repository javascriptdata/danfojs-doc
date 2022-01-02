---
description: Capitalize the first character of each string
---

# Series.str.capitalize

> danfo.Series.str.**capitalize**(options)       \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L46)]

| Parameters | Type   | Description                                                     | Default                                                |
| ---------- | ------ | --------------------------------------------------------------- | ------------------------------------------------------ |
| options    | Object | **inplace**: Whether to perform the operation in-place or not.  | <p>{</p><p><strong>inplace</strong>: false</p><p>}</p> |

**Returns**:  Series (String element)

**Example**

Convert  the first character of a string to capital letter

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower boy', 'capitals', 'sentence', 'swApCaSe']
let sf = new dfd.Series(data)
sf.str.capitalize().print()
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
║ 0 │ Lower boy            ║
╟───┼──────────────────────╢
║ 1 │ Capitals             ║
╟───┼──────────────────────╢
║ 2 │ Sentence             ║
╟───┼──────────────────────╢
║ 3 │ Swapcase             ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
