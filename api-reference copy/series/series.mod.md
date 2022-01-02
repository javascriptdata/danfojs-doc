---
description: Return Modulo of series and other, element-wise (binary operator mod).
---

# Series.mod

> danfo.Series.mod(other, options)  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L235)]

| Parameters | Type               | Description                                                                                    | Default                               |
| ---------- | ------------------ | ---------------------------------------------------------------------------------------------- | ------------------------------------- |
| other      | Series\|int\|float | values                                                                                         |                                       |
| options    | Object             | inplace: Boolean indicating whether to perform the operation inplace or not. Defaults to false | <p>{</p><p>inplace: false</p><p>}</p> |

**Return:** Series

**Example**

Modulus with values of another series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [2, 30, 4, 5]
let data2 = [1.1, 2.2, 3.3, 2.4]
let sf1 = new dfd.Series(data1)
let sf2 = new dfd.Series(data2)
sf1.mod(sf2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 0.8999999761581421   ║
╟───┼──────────────────────╢
║ 1 │ 1.3999993801116943   ║
╟───┼──────────────────────╢
║ 2 │ 0.7000000476837158   ║
╟───┼──────────────────────╢
║ 3 │ 0.19999980926513672  ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

Modulo with a value

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [1, 2, 3, 4, 5]
let sf1 = new dfd.Series(data1)

sf1.mod(2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 1                    ║
╟───┼──────────────────────╢
║ 1 │ 0                    ║
╟───┼──────────────────────╢
║ 2 │ 1                    ║
╟───┼──────────────────────╢
║ 3 │ 0                    ║
╟───┼──────────────────────╢
║ 4 │ 1                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
