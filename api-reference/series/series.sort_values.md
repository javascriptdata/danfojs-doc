---
description: Sort a Series in ascending or descending order
---

# Series.sort\_values

> danfo.Series.sort\_values\(kwargs\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L511)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| kwargs\["inplace"\] | Boolean | return new series or not | false |
| kwargs\["ascending"\] | Boolean | select if to sort by ascending or descending | true |

  **Return:** Series

**Examples**

Sort series values using the default settings

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [20, 30, 1, 2, 4, 57, 89, 0, 4]
let sf1 = new dfd.Series(data1)
let sf2 = sf1.sort_values()

sf2.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 7 │ 0                    ║
╟───┼──────────────────────╢
║ 2 │ 1                    ║
╟───┼──────────────────────╢
║ 3 │ 2                    ║
╟───┼──────────────────────╢
║ 4 │ 4                    ║
╟───┼──────────────────────╢
║ 8 │ 4                    ║
╟───┼──────────────────────╢
║ 0 │ 20                   ║
╟───┼──────────────────────╢
║ 1 │ 30                   ║
╟───┼──────────────────────╢
║ 5 │ 57                   ║
╟───┼──────────────────────╢
║ 6 │ 89                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

Sort series value without returning a new series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [20, 30, 1, 2, 4, 57, 89, 0, 4]
let sf1 = new dfd.Series(data1)
sf1.sort_values({ "inplace": true })

sf1.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 7 │ 0                    ║
╟───┼──────────────────────╢
║ 2 │ 1                    ║
╟───┼──────────────────────╢
║ 3 │ 2                    ║
╟───┼──────────────────────╢
║ 4 │ 4                    ║
╟───┼──────────────────────╢
║ 8 │ 4                    ║
╟───┼──────────────────────╢
║ 0 │ 20                   ║
╟───┼──────────────────────╢
║ 1 │ 30                   ║
╟───┼──────────────────────╢
║ 5 │ 57                   ║
╟───┼──────────────────────╢
║ 6 │ 89                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

Sort series value in descending order

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [20, 30, 1, 2, 4, 57, 89, 0, 4]
let sf1 = new dfd.Series(data1)
sf1.sort_values({ "ascending": false, "inplace": true })

sf1.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 6 │ 89                   ║
╟───┼──────────────────────╢
║ 5 │ 57                   ║
╟───┼──────────────────────╢
║ 1 │ 30                   ║
╟───┼──────────────────────╢
║ 0 │ 20                   ║
╟───┼──────────────────────╢
║ 8 │ 4                    ║
╟───┼──────────────────────╢
║ 4 │ 4                    ║
╟───┼──────────────────────╢
║ 3 │ 2                    ║
╟───┼──────────────────────╢
║ 2 │ 1                    ║
╟───┼──────────────────────╢
║ 7 │ 0                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

