---
description: Replaces values in a DataFrame with specified values
---

# DataFrame.replace

> danfo.DataFrame.**replace**(oldValue, newValue, options)

| Parameters | Type                    | Description                                                                                                                                                                                                                                                | Default          |
| ---------- | ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------- |
| oldValue   | String, boolean, Number | The value you want to replace                                                                                                                                                                                                                              |                  |
| newValue   | String, boolean, Number | The new value you want to replace the old value with                                                                                                                                                                                                       |                  |
| options    | Object                  | <p><strong>columns:</strong> Array<strong>.</strong> An array of column names to replace, If not specified, replace all columns.</p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p> | {inplace: false} |

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    "Col1": [10, 45, 56, 10],
    "Col2": [23, 20, 10, 24]
}
let df = new dfd.DataFrame(data)

let df_rep = df.replace(10, -999, { columns: ["Col1"] })

df_rep.print()
 
 
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
╔═══╤═══════════════════╤═══════════════════╗
║   │ Col1              │ Col2              ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ -999              │ 23                ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 45                │ 20                ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 56                │ 10                ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ -999              │ 24                ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

If a column name is not specified, **replace** works on all columns:

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [["A", "A", "A", "B"], ["B", "C", "C", "D"]]
let df = new dfd.DataFrame(data)
//replace value in all column
let df_rep = df.replace("A", "BOY")

df_rep.print()
```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```javascript
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ 0                 │ 1                 │ 2                 │ 3                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ BOY               │ BOY               │ BOY               │ B                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ B                 │ C                 │ C                 │ D                 ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
