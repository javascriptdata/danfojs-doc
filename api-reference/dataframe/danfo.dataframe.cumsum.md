---
description: Return cumulative sum over a DataFrame or Series axis.
---

# DataFrame.cumsum

danfo.DataFrame.**cumsum**\(kwargs\) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L706)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| kwargs | Object | {**axis**: 0 for row and 1 for column} | {axis: 1} |

**Returns:**

       ****return **DataFrame**

## **Examples**

## Cumulative sum of elements along default axis \(row\)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
let new_df = df.cumsum({ axis: 0 })

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
```text
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 11                │ 20                │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 12                │ 35                │ 9                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 14                │ 65                │ 49                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 16                │ 154               │ 127               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

## Cumulative sum of elements along column axis \(1\)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
let new_df = df.cumsum({ axis: 1 })

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
```text
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 11                │ 31                │ 34                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 16                │ 22                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 32                │ 72                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 2                 │ 91                │ 169               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

