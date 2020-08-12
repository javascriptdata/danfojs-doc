---
description: 'Return Multiplication of series and other, element-wise (binary operator mul).'
---

# Series.mul

> danfo.Series.mul\(other\)  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L168)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| other | Series\|int\| | values  |  |

**Return:** Series

**Example**

multiplication with values of another series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [30, 40, 3, 5]
let data2 = [1, 2, 3, 4]
let sf1 = new dfd.Series(data1)
let sf2 = new dfd.Series(data2)
sf1.mul(sf2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 30                   ║
╟───┼──────────────────────╢
║ 1 │ 80                   ║
╟───┼──────────────────────╢
║ 2 │ 9                    ║
╟───┼──────────────────────╢
║ 3 │ 20                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

multiply with a value

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [1, 2, 3, 4, 5]
let sf1 = new dfd.Series(data1)

sf1.mul(2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 2                    ║
╟───┼──────────────────────╢
║ 1 │ 4                    ║
╟───┼──────────────────────╢
║ 2 │ 6                    ║
╟───┼──────────────────────╢
║ 3 │ 8                    ║
╟───┼──────────────────────╢
║ 4 │ 10                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}



