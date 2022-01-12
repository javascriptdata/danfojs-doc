---
description: Return cumulative product over a DataFrame or Series axis.
---

# DataFrame.cumProd

danfo.DataFrame.**cumProd**(options) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L706)]

| Parameters | Type   | Description                                                                                                                                                                    | Default                   |
| ---------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------- |
| options    | Object | <p><strong>axis</strong>: 0 for row and 1 for column</p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p> | {axis: 1, inplace: false} |

## **Examples**

## Cumulative product of elements along default axis 1 (column)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
let cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
let new_df = df.cumProd()

new_df.print()
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
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ 11                │ 220               │ 660               ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ 1                 │ 15                │ 90                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ 2                 │ 60                │ 2400              ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ 2                 │ 178               │ 13884             ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

## Cumulative product of elements along column axis (1)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
let cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
let new_df = df.cumProd({ axis: 1 })

new_df.print()
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
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ 11                │ 220               │ 660               ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ 1                 │ 15                │ 90                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ 2                 │ 60                │ 2400              ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ 2                 │ 178               │ 13884             ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
