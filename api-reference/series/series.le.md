---
description: Check if all the values in a series is less than or equal to a value
---

# Series.le

> danfo.Series.ge\(other\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L865)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| other | Series**\|** int\|float | value\(s\) to compare |  |

**Returns:** Series \(Boolean Element\)

**Example**

Check if all the values in a series is less than or equal to a value

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf1 = new dfd.Series(data1)

sf1.le(20).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ true                 ║
╟───┼──────────────────────╢
║ 1 │ false                ║
╟───┼──────────────────────╢
║ 2 │ false                ║
╟───┼──────────────────────╢
║ 3 │ false                ║
╟───┼──────────────────────╢
║ 4 │ false                ║
╟───┼──────────────────────╢
║ 5 │ true                 ║
╟───┼──────────────────────╢
║ 6 │ true                 ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

check if all the values in a series are less than equal to values in another series.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [10, 45, 56, 25, 23, 20, 10]
let data2 = [10, 450, 56, 5, 25, 2, 0]
let sf1 = new dfd.Series(data1)
let sf2 = new dfd.Series(data2)

sf1.le(sf2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ true                 ║
╟───┼──────────────────────╢
║ 1 │ true                 ║
╟───┼──────────────────────╢
║ 2 │ true                 ║
╟───┼──────────────────────╢
║ 3 │ false                ║
╟───┼──────────────────────╢
║ 4 │ true                 ║
╟───┼──────────────────────╢
║ 5 │ false                ║
╟───┼──────────────────────╢
║ 6 │ false                ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

