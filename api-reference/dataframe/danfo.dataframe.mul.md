---
description: 'Get Multiplication of dataframe and other, element-wise (binary operator mul).'
---

# DataFrame.mul

danfo.DataFrame.**mul**\(axis\) \[[source](https://github.com/opensource9ja/danfojs/blob/fe56860b0a303d218d60ba71dee6abf594401556/danfojs/src/core/frame.js#L383)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| other | DataFrame, Series, Array or Scalar | Object to modulo with |  |
| axis | Int | 0 for row, 1 for column | 0 |

**Returns:**

       ****return **DataFrame**

## **Examples**

### Multiplication of ****DataFrame with a scalar value

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"Col1": [10, 45, 56, 10],
            "Col2": [23, 20, 10, 24]}
let df = new dfd.DataFrame(data)

let df_new = df.mul(2)

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
║ 0 │ 20                │ 46                ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 90                │ 40                ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 112               │ 20                ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 20                │ 48                ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Multiplication of  ****DataFrame with a Series along the column axis

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


let data = { "Col1": [1, 4, 5, 1],
             "Col2": [3, 2, 0, 4] }

let df = new dfd.DataFrame(data)
let sf = new dfd.Series([4, 5])

let df_new = df.mul(sf, axis = 1)

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
║ 0 │ 4                 │ 15                ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 16                │ 10                ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 20                │ 0                 ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 4                 │ 20                ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Multiplication of  ****DataFrame with a DataFrame

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

let df_new = df.mul(df2)

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
║ 0 │ 1                 │ 40                ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 20                │ 0                 ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 100               │ 1                 ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 0                 │ 8                 ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Multiplication of ****DataFrame with a JavaScript Array

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"Col1": [10, 45, 56, 10],
            "Col2": [23, 20, 10, 24]}

let df = new dfd.DataFrame(data)
let val = [2,2]

let df_new = df.mul(val, axis=1)

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
║ 0 │ 20                │ 46                ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 90                │ 40                ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 112               │ 20                ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 20                │ 48                ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
