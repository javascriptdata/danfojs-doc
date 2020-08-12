---
description: >-
  Get Float division of DataFrame and other, element-wise (binary operator
  truediv).
---

# DataFrame.div

danfo.DataFrame.**div**\(axis\) \[[source](https://github.com/opensource9ja/danfojs/blob/fe56860b0a303d218d60ba71dee6abf594401556/danfojs/src/core/frame.js#L401)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| other | DataFrame, Series, Array or Scalar | Object to modulo with |  |
| axis | Int | 0 for row, 1 for column | 0 |

**Returns:**

       ****return **DataFrame**

## **Examples**

### Division of ****DataFrame with a scalar value:

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"Col1": [10, 45, 56, 10],
            "Col2": [23, 20, 10, 24]}
            
let df = new dfd.DataFrame(data)

let df_new = df.div(2)

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
║ 0 │ 5                 │ 11.5              ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 22.5              │ 10                ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 28                │ 5                 ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 5                 │ 12                ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Division of  ****DataFrame with a Series along the column axis:

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


let data = { "Col1": [1, 4, 5, 1],
            "Col2": [3, 2, 0, 4] }
            
let df = new dfd.DataFrame(data)
let sf = new dfd.Series([4, 5])

let df_new = df.div(sf, axis = 1)

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
║ 0 │ 0.25              │ 0.60000002384...  ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 0.40000000596...  ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 1.25              │ 0                 ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 0.25              │ 0.80000001192...  ║
╚═══╧═══════════════════╧═══════════════════╝

```
{% endtab %}
{% endtabs %}

### Division of  ****DataFrame with a DataFrame

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"Col1": [1, 4, 5, 0],
            "Col2": [2, 0, 1, 4]}
            
let data2 = {"new_col1": [1, 5, 20, 10],
             "new_Col2": [20, 2, 1, 2]}

let df = new dfd.DataFrame(data)
let df2 = new dfd.DataFrame(data2)

let df_new = df.div(df2)

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
║ 0 │ 1                 │ 0.10000000149...  ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 0.80000001192...  │ 0                 ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 0.25              │ 1                 ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 0                 │ 2                 ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Division of ****DataFrame with a JavaScript Array

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"Col1": [10, 45, 56, 10],
            "Col2": [23, 20, 10, 24]}
            
let df = new dfd.DataFrame(data)
let val = [2,2]

let df_new = df.div(val, axis=1)

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
║ 0 │ 5                 │ 11.5              ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 22.5              │ 10                ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 28                │ 5                 ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 5                 │ 12                ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}



