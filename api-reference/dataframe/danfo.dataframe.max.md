---
description: Return the maximum of the values for the requested axis.
---

# DataFrame.max

danfo.DataFrame.**max**(options)&#x20;

| Parameters | Type   | Description                                                                         | Default     |
| ---------- | ------ | ----------------------------------------------------------------------------------- | ----------- |
| options    | Object | **axis:** 0 or 1. If 0, compute the mean column-wise, if 1, row-wise. Defaults to 1 | { axis: 1 } |

## **Examples**

## Return the maximum value along default axis 1 (column)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
let cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
df.print()
df.max().print()
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
║ 0 │ 20 ║
╟───┼────╢
║ 1 │ 15 ║
╟───┼────╢
║ 2 │ 40 ║
╟───┼────╢
║ 3 │ 89 ║
╚═══╧════╝

```
{% endtab %}
{% endtabs %}

## Return the maximum value along row axis (0)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
let data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
let cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
df.print()
df.max({ axis: 0 }).print()
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
║ A │ 11 ║
╟───┼────╢
║ B │ 89 ║
╟───┼────╢
║ C │ 78 ║
╚═══╧════╝
```
{% endtab %}
{% endtabs %}
