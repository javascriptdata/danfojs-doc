---
description: Return cumulative maximum over a DataFrame or Series axis.
---

# DataFrame.cummax

danfo.DataFrame.**cummax**(options) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L706)]

| Parameters | Type   | Description                                                                                                                                                                           | Default                   |
| ---------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------- |
| options    | Object | <p><strong>axis</strong>: 0 for row and 1 for column</p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p><p></p> | {axis: 1, inplace: false} |

**Returns:**

&#x20;      ****       return **DataFrame**

## **Examples**

## Cumulative maximum of elements along default axis (row)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
let new_df = df.cummax({ axis: 0 })

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
║ 1 │ 11                │ 20                │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 11                │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 11                │ 89                │ 78                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

## Cumulative maximum of elements along column axis (1)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
let new_df = df.cummax({ axis: 1 })

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
║ 0 │ 11                │ 20                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 15                │ 15                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 2                 │ 89                │ 89                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
