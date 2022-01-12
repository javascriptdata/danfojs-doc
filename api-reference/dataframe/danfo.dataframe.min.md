---
description: Return the minimum of the values for the requested axis.
---

# DataFrame.min

danfo.DataFrame.**min**(options)

| Parameters | Type   | Description                                                                         | Default     |
| ---------- | ------ | ----------------------------------------------------------------------------------- | ----------- |
| options    | Object | **axis:** 0 or 1. If 0, compute the mean column-wise, if 1, row-wise. Defaults to 1 | { axis: 1 } |

## **Examples**

## Returns the minimum value along default axis 1 (column)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
let cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
df.print()
df.min().print()
```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 11                │ 20                │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 15                │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 2                 │ 89                │ 78                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝

╔═══╤═══╗
║ 0 │ 3 ║
╟───┼───╢
║ 1 │ 1 ║
╟───┼───╢
║ 2 │ 2 ║
╟───┼───╢
║ 3 │ 2 ║
╚═══╧═══╝
```
{% endtab %}
{% endtabs %}

## Return the minimum value along row axis (0)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
let cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
df.print()
df.min({ axis: 0 }).print()
```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 11                │ 20                │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 15                │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 2                 │ 89                │ 78                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝

╔═══╤════╗
║ A │ 1  ║
╟───┼────╢
║ B │ 15 ║
╟───┼────╢
║ C │ 3  ║
╚═══╧════╝
```
{% endtab %}
{% endtabs %}
