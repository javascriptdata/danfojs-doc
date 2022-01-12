---
description: Return cumulative maximum over a DataFrame or Series axis.
---

# DataFrame.cumMax

danfo.DataFrame.cumMax(options)&#x20;

| Parameters | Type   | Description                                                                                                                                                                    | Default                   |
| ---------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------- |
| options    | Object | <p><strong>axis</strong>: 0 for row and 1 for column</p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p> | {axis: 1, inplace: false} |

**Returns:**

\*\*\*\* return **DataFrame**

## **Examples**

## Cumulative maximum of elements along axis (row)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
let cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
let new_df = df.cumMax({ axis: 0 })

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

let data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
let cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
let new_df = df.cumMax({ axis: 1 })

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
