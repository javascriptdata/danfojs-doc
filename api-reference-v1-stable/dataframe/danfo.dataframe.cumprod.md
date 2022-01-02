---
description: Return cumulative product over a DataFrame or Series axis.
---

# DataFrame.cumprod

danfo.DataFrame.**cumprod**(options) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L706)]

| Parameters | Type   | Description                                                                                                                                                                           | Default                   |
| ---------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------- |
| options    | Object | <p><strong>axis</strong>: 0 for row and 1 for column</p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p><p></p> | {axis: 1, inplace: false} |

**Returns:**

&#x20;      ****       return **DataFrame**

## **Examples**

## Cumulative product of elements along default axis (row)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

data = [[1, 2, 3], [1, 5, 6], [2, 30, 40], [2, 89, 78]]
cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
let new_df = df.cumprod()

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
║ 0 │ 1                 │ 2                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 10                │ 18                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 300               │ 720               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 4                 │ 26700             │ 56160             ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

## Cumulative product of elements along column axis (1)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

data = [[1, 2, 3], [1, 5, 6], [2, 30, 40], [2, 89, 78]]
cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
let new_df = df.cumprod({axis: 1})

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
║ 0 │ 1                 │ 2                 │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 5                 │ 30                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 60                │ 2400              ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 2                 │ 178               │ 13884             ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
