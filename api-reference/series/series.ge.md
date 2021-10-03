---
description: Check if all the values in a series is greater than or equal a value
---

# Series.ge

> danfo.Series.ge\(other\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L874)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| other | Series, Array or number | value\(s\) to compare |  |

**Returns:** Series \(Boolean element\)

**Example**

Compare all the value in a Series to the values in another series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, 56, 25, 23, 20, 10]
let data2 = [10, 450, 56, 5, 25, 2, 0]
let sf1 = new dfd.Series(data1)
let sf2 = new dfd.Series(data2)

sf1.ge(sf2).print()
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
║ 2 │ true                 ║
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

Check if all the value in a Series is greater than or equal a value.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf1 = new dfd.Series(data1)

sf1.ge(20).print()
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
║ 5 │ true                 ║
╟───┼──────────────────────╢
║ 6 │ false                ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

