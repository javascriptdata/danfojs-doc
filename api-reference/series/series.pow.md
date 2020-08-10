---
description: >-
  Return Exponential power of series and other, element-wise (binary operator
  pow).
---

# Series.pow

> danfo.Series.pow\(other\)  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L216)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| other | Series\|int\| | values  |  |

**Return:** Series

**Example**

Exponential power with values of another series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [2, 3, 4, 5]
let data2 = [1, 2, 3, 0]
let sf1 = new dfd.Series(data1)
let sf2 = new dfd.Series(data2)
sf1.pow(sf2).print()
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
║ 1 │ 9                    ║
╟───┼──────────────────────╢
║ 2 │ 64                   ║
╟───┼──────────────────────╢
║ 3 │ 1                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

Exponential value with a value

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [1, 2, 3, 4, 5]
let sf1 = new dfd.Series(data1)

sf1.pow(2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 1                    ║
╟───┼──────────────────────╢
║ 1 │ 4                    ║
╟───┼──────────────────────╢
║ 2 │ 9                    ║
╟───┼──────────────────────╢
║ 3 │ 16                   ║
╟───┼──────────────────────╢
║ 4 │ 25                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

