---
description: Check if all the value in a series is greater than a value
---

# Series.gt

> danfo.Series.gt\(other\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L856)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| other | Series, Array or number | value\(s\) to compare |  |

**Returns**: Series \(boolean element\)

**Example**

Check if all the values in a series are greater than a value

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf1 = new dfd.Series(data1)

sf1.gt(20).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ false                ║
╟───┼──────────────────────╢
║ 1 │ true                 ║
╟───┼──────────────────────╢
║ 2 │ true                 ║
╟───┼──────────────────────╢
║ 3 │ true                 ║
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

check if all the values in a series are greater than values in another series.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, 56, 25, 23, 20, 10]
let data2 = [10, 450, 56, 5, 25, 2, 0]
let sf1 = new dfd.Series(data1)
let sf2 = new dfd.Series(data2)

sf1.gt(sf2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ false                ║
╟───┼──────────────────────╢
║ 1 │ false                ║
╟───┼──────────────────────╢
║ 2 │ false                ║
╟───┼──────────────────────╢
║ 3 │ true                 ║
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

