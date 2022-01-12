---
description: >-
  Get Less than or Equal to of DataFrame and other, element-wise (binary
  operator eq).
---

# DataFrame.le

danfo.DataFrame.le(other, option)

| Parameters | Type                             | Description                                                 | Default   |
| ---------- | -------------------------------- | ----------------------------------------------------------- | --------- |
| other      | DataFrame, Series, Array, Scalar | Data structure, or array-like object to compare against     |           |
| option     | Object                           | **axis**: 0 or 1. If 0, add column-wise, if 1, add row-wise | {axis: 1} |

## **Examples**

### Comparing a DataFrame with a scalar value:

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"Col1": [10, 45, 56, 10],
            "Col2": [23, 20, 10, 24]}
            
let df = new dfd.DataFrame(data)

let df_rep = df.le(20)

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
║ 0 │ true              │ false             ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ false             │ true              ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ false             │ true              ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ true              │ false             ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Comparing a DataFrame with a Series along the column axis:

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"Col1": [10, 45, 56, 10],
            "Col2": [23, 20, 10, 24]}
            
let df = new dfd.DataFrame(data)
let sf = new dfd.Series([10,40])

let df_rep = df.le(sf, {axis:1})

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
║ 0 │ true              │ true              ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ false             │ true              ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ false             │ true              ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ true              │ true              ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Comparing a DataFrame with another DataFrame

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

let df_rep = df.le(df2)

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
║ 0 │ true              │ true              ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ true              │ false             ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ true              │ true              ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ true              │ true              ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Comparing a DataFrame with an Array

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"Col1": [10, 45, 56, 10],
            "Col2": [23, 20, 10, 24]}
let df = new dfd.DataFrame(data)
let val = [10,40]

let df_rep = df.le(val, {axis:1})

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
║ 0 │ true              │ true              ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ false             │ true              ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ false             │ true              ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ true              │ true              ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
