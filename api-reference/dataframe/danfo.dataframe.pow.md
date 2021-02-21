---
description: >-
  Get Exponential power of dataframe and other, element-wise (binary operator
  pow).
---

# DataFrame.pow

danfo.DataFrame.**pow**\(axis\) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L418)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| other | DataFrame, Series, Array or Scalar | Object to modulo with |  |
| axis | Int | 0 for row, 1 for column | 0 |

**Returns:**

       ****return **DataFrame**

## **Examples**

### Exponent of ****DataFrame with a scalar value

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"Col1": [10, 45, 56, 10],
            "Col2": [23, 20, 10, 24]}

let df = new dfd.DataFrame(data)

let df_new = df.pow(2)

df_new.print()
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
╔═══╤═══════════════════╤═══════════════════╗
║   │ Col1              │ Col2              ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ 100               │ 529               ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 2025              │ 400               ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 3136              │ 100               ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 100               │ 576               ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Exponent of  ****DataFrame with a Series along the column axis

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


let data = { "Col1": [1, 4, 5, 1],
             "Col2": [3, 2, 0, 4] }
let df = new dfd.DataFrame(data)
let sf = new dfd.Series([4, 5])

let df_new = df.pow(sf, axis = 1)

df_new.print()
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
╔═══╤═══════════════════╤═══════════════════╗
║   │ Col1              │ Col2              ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ 1                 │ 243               ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 256               │ 32                ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 625               │ 0                 ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 1                 │ 1024              ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Exponent of  ****DataFrame with a DataFrame

{% tabs %}
{% tab title="Node" %}
```javascript
let data = { "Col1": [1, 4, 5, 1],
             "Col2": [3, 2, 0, 4] }

let data2 = {"new_col1": [1, 5, 20, 10],
             "new_Col2": [20, 2, 1, 2]}

let df = new dfd.DataFrame(data)
let df2 = new dfd.DataFrame(data2)

let df_new = df.pow(df2)

df_new.print()

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
╔═══╤═══════════════════╤═══════════════════╗
║   │ Col1              │ Col2              ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ 1                 │ 1048576           ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 1024              │ 0                 ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 95367433551872    │ 1                 ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 0                 │ 16                ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Exponent of ****DataFrame with a JavaScript Array

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"Col1": [10, 45, 56, 10],
            "Col2": [23, 20, 10, 24]}

let df = new dfd.DataFrame(data)
let val = [2,2]

let df_new = df.pow(val, axis=1)

df_new.print()
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
╔═══╤═══════════════════╤═══════════════════╗
║   │ Col1              │ Col2              ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ 100               │ 12167             ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 2025              │ 8000              ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 3136              │ 1000              ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 100               │ 13824             ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
