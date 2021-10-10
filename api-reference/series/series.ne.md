---
description: Check if all values in a  series is not equal to a value(s)
---

# Series.ne

> danfo.Series.ne(other)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L883)]

| Parameters | Type                    | Description       | Default |
| ---------- | ----------------------- | ----------------- | ------- |
| other      | Series, Array or number |  value to compare |         |

**Returns**: Series (Boolean element)

**Example**

Compare all the values in a series to that in another series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, 56, 25, 23, 20, 10]
let data2 = [10, 450, 56, 5, 25, 2, 0]
let sf1 = new dfd.Series(data1)
let sf2 = new dfd.Series(data2)

sf1.ne(sf2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ false                ║
╟───┼──────────────────────╢
║ 1 │ true                 ║
╟───┼──────────────────────╢
║ 2 │ false                ║
╟───┼──────────────────────╢
║ 3 │ true                 ║
╟───┼──────────────────────╢
║ 4 │ true                 ║
╟───┼──────────────────────╢
║ 5 │ true                 ║
╟───┼──────────────────────╢
║ 6 │ true                 ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

Compare all the values in a Series to a value.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf1 = new dfd.Series(data1)

sf1.ne(10).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
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
