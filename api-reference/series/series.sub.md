---
description: 'Return Subtraction of series and other, element-wise (binary operator sub).'
---

# Series.sub

> danfo.Series.sub\(other\)  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L148)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| other | Series\|int\| | values  |  |

**Return:** Series

**Example**

subtract from values of another series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [30, 40, 3, 5]
let data2 = [1, 2, 3, 4]
let sf1 = new dfd.Series(data1)
let sf2 = new dfd.Series(data2)
sf1.sub(sf2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 29                   ║
╟───┼──────────────────────╢
║ 1 │ 38                   ║
╟───┼──────────────────────╢
║ 2 │ 0                    ║
╟───┼──────────────────────╢
║ 3 │ 1                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

subtract from a value

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [1, 2, 3, 4, 5]
let sf1 = new dfd.Series(data1)

sf1.sub(2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ -1                   ║
╟───┼──────────────────────╢
║ 1 │ 0                    ║
╟───┼──────────────────────╢
║ 2 │ 1                    ║
╟───┼──────────────────────╢
║ 3 │ 2                    ║
╟───┼──────────────────────╢
║ 4 │ 3                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}



