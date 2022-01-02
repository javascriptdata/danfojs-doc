---
description: Return cumulative minimum over a DataFrame or Series axis.
---

# DataFrame.cummin

danfo.DataFrame.**cummin**(options) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L706)]

| Parameters | Type   | Description                                                                                                                                                                           | Default                   |
| ---------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------- |
| options    | Object | <p><strong>axis</strong>: 0 for row and 1 for column</p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p><p></p> | {axis: 1, inplace: false} |

**Returns:**

&#x20;      ****       return **DataFrame**

## **Examples**

## Cumulative minimum of elements along default axis (row)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
let new_df = df.cummin({ axis: 0 })

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
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 11                │ 20                │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 15                │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 1                 │ 15                │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 1                 │ 15                │ 3                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

## Cumulative minimum of elements along column axis (1)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
let new_df = df.cummin({ axis: 1 })

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
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 11                │ 11                │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 1                 │ 1                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 2                 │ 2                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 2                 │ 2                 │ 2                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
