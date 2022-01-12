---
description: Remove missing values (NaNs, undefined, null) for DataFrame
---

# DataFrame.dropNa

danfo.DataFrame.**dropNa**(axis, options) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L1430)]

| Parameters | Type   | Description                                                                                        | Default              |
| ---------- | ------ | -------------------------------------------------------------------------------------------------- | -------------------- |
| axis       | Int    | 0 or 1. If 0, drop columns with NaNs, if 1, drop rows with NaNs                                    | 1                    |
| options    | Object | **inplace**: Boolean indicating whether to perform the operation inplace or not. Defaults to false | {**inplace:** false} |

## **Examples**

### Drop rows (axis=0) with missing values

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [[1, 2, 3], [NaN, 5, 6], [NaN, 30, 40], [39, NaN, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

df.print()

let df_drop = df.dropNa({ axis: 0 })
df_drop.print()
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
║ 0          │ 1                 │ 2                 │ 3                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ NaN               │ 5                 │ 6                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ NaN               │ 30                │ 40                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ 39                │ NaN               │ 78                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

╔════════════╤═══════════════════╗
║            │ C                 ║
╟────────────┼───────────────────╢
║ 0          │ 3                 ║
╟────────────┼───────────────────╢
║ 1          │ 6                 ║
╟────────────┼───────────────────╢
║ 2          │ 40                ║
╟────────────┼───────────────────╢
║ 3          │ 78                ║
╚════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Drop columns (axis=1) with missing values

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [[1, 2, 3], [NaN, 5, 6], [NaN, 30, 40], [39, NaN, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

df.print()

df.dropNa({ axis: 1, inplace: true })
df.print()
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
║ 0          │ 1                 │ 2                 │ 3                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ NaN               │ 5                 │ 6                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ NaN               │ 30                │ 40                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ 39                │ NaN               │ 78                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ 1                 │ 2                 │ 3                 ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
