---
description: Check all the values in a series is equal to another value
---

# Series.eq

> danfo.Series.eq\(other\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L894)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| other | Series**\|** int\|String\|float |  value to compare |  |

**Returns**: Series \(Boolean element\)

**Examples**

Compare all the values in a series to another series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, 56, 25, 23, 20, 10]
let data2 = [10, 450, 56, 5, 25, 2, 0]
let sf1 = new dfd.Series(data1)
let sf2 = new dfd.Series(data2)

sf1.eq(sf2).print()
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
║ 3 │ false                ║
╟───┼──────────────────────╢
║ 4 │ false                ║
╟───┼──────────────────────╢
║ 5 │ false                ║
╟───┼──────────────────────╢
║ 6 │ false                ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

Check it all the values are equal to a value

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf1 = new dfd.Series(data1)

sf1.eq(10).print()
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
║ 5 │ false                ║
╟───┼──────────────────────╢
║ 6 │ true                 ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

