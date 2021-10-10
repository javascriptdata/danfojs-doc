---
description: Replaces values in a DataFrame with specified values
---

# DataFrame.replace

> danfo.DataFrame.**replace**(kwargs) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L1670)]

| Parameters | Type   | Description                                                                                                                                                                                                                                                                                                        | Default |
| ---------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------- |
| kwargs     | Object | <p> {<strong>replace: </strong>int, float, str.<strong> </strong>The value to replace.</p><p>  <strong>with</strong>: Int, float, str. The new value to replace with.</p><p>  <strong>in: </strong>Array<strong>. </strong>An array of column names to replace, If not specified, replace all columns.</p><p>}</p> |         |

**Returns:**

**       **return** DataFrame**

****

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"Col1": [10, 45, 56, 10],
            "Col2": [23, 20, 10, 24]}
let df = new dfd.DataFrame(data)

let df_rep = df.replace({ "replace": 10, "with": -999, "in": ["Col1"] })

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

By not specifying a** **column**, **the** **replace works on all columns ** **

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-js")


let data = [["A", "A", "A", "B"], ["B", "C", "C", "D"]]
let df = new dfd.DataFrame(data)
//replace value in all column
let df_rep = df.replace({ "replace": "A", "with": "boy" })

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

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ 0                 │ 1                 │ 2                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ boy               │ boy               │ boy               │ B                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ B                 │ C                 │ C                 │ D                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
