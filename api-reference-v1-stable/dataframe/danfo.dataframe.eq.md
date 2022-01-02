---
description: Get Equal to of DataFrame and other, element-wise (binary operator eq).
---

# DataFrame.eq

danfo.DataFrame.eq(other, option) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L1566)]

| Parameters | Type                             | Description                                                 | Default   |
| ---------- | -------------------------------- | ----------------------------------------------------------- | --------- |
| other      | DataFrame, Series, Array, Scalar | Data structure, or array-like object to compare against     |           |
| option     | Object                           | **axis**: 0 or 1. If 0, add column-wise, if 1, add row-wise | {axis: 1} |

**Returns:**

****

## **Examples**

### Comparing** **DataFrame with a scalar value:

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"Col1": [10, 45, 56, 10],
            "Col2": [23, 20, 10, 24]}
let df = new dfd.DataFrame(data)

let df_rep = df.eq(20)

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
║ 0 │ false             │ false             ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ false             │ true              ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ false             │ false             ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ false             │ false             ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Comparing** **DataFrame with a Series along the column axis:

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"Col1": [10, 45, 56, 10],
            "Col2": [23, 20, 10, 24]}
let df = new dfd.DataFrame(data)
let sf = new dfd.Series([10,40])

let df_rep = df.eq(sf, {axis:1})

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
╔═══╤═══════════════════╤═══════════════════╗
║   │ Col1              │ Col2              ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ true              │ false             ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ false             │ false             ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ false             │ false             ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ true              │ false             ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Comparing** **DataFrame with a DataFrame

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"Col1": [10, 45, 56, 10],
            "Col2": [23, 20, 10, 24]}
let data2 = {"new_col1": [10, 45, 200, 10],
            "new_Col2": [230, 200, 110, 24]}

let df = new dfd.DataFrame(data)
let df2 = new dfd.DataFrame(data2)

let df_rep = df.eq(df2)

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
╔═══╤═══════════════════╤═══════════════════╗
║   │ Col1              │ Col2              ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ true              │ false             ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ true              │ false             ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ false             │ false             ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ true              │ true              ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Comparing** **DataFrame with a JavaScript Array

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"Col1": [10, 45, 56, 10],
            "Col2": [23, 20, 10, 24]}
let df = new dfd.DataFrame(data)
let val = [10,40]

let df_rep = df.eq(val, {axis:1})

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
╔═══╤═══════════════════╤═══════════════════╗
║   │ Col1              │ Col2              ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ true              │ false             ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ false             │ false             ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ false             │ false             ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ true              │ false             ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
