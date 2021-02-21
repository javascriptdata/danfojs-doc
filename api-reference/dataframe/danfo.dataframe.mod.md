---
description: 'Get Modulo of DataFrame and other, element-wise (binary operator mod).'
---

# DataFrame.mod

danfo.DataFrame.**mod**\(axis\) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L436)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| other | DataFrame, Series, Array or Scalar | Object to modulo with |  |
| axis | Int | 0 for row, 1 for column | 0 |

**Returns:**

       ****return **DataFrame**

## **Examples**

### Modulo of ****DataFrame with a scalar value

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"Col1": [10, 45, 56, 10],
            "Col2": [23, 20, 10, 24]}

let df = new dfd.DataFrame(data)

let df_new = df.mod(2)

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
║ 0 │ 0                 │ 1                 ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 0                 ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 0                 │ 0                 ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Modulo of  ****DataFrame with a Series along the column axis

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")


let data = {"Col1": [10, 45, 56, 10],
            "Col2": [23, 20, 10, 24]}]

let df = new dfd.DataFrame(data)
let sf = new dfd.Series([10,40])

let df_new = df.mod(sf, axis=1)

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
║ 0 │ 0                 │ 23                ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 5                 │ 20                ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 6                 │ 10                ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 0                 │ 24                ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Modulo of  ****DataFrame with a DataFrame

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

let df_new = df.mod(df2)

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
```javascript
╔═══╤═══════════════════╤═══════════════════╗
║   │ Col1              │ Col2              ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ 0                 │ 23                ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 0                 │ 20                ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 56                │ 10                ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 0                 │ 0                 ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Modulo of ****DataFrame with a JavaScript Array

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"Col1": [10, 45, 56, 10],
            "Col2": [23, 20, 10, 24]}

let df = new dfd.DataFrame(data)
let val = [10,40]

let df_new = df.mod(val, axis=1)

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
```javascript
╔═══╤═══════════════════╤═══════════════════╗
║   │ Col1              │ Col2              ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ 0                 │ 23                ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 5                 │ 20                ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 6                 │ 10                ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 0                 │ 24                ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
