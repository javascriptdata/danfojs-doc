---
description: 'Get Not Equal to of DataFrame and other, element-wise (binary operator eq).'
---

# DataFrame.ne

danfo.DataFrame.ne\(other, axis\) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L1633)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| other | DataFrame, Series, Array, Scalar | Data structure, or array-like object to compare against |  |
| axis | Int | Whether to compare by the index \(0\) or columns \(1\). | 0 |

**Returns:**

       ****return **DataFrame**

## **Examples**

### Comparing ****DataFrame with a scalar value:

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [{"Col1": [10, 45, 56, 10]}, {"Col2": [23, 20, 10, 24]}]
let df = new dfd.DataFrame(data)

let df_rep = df.ne(20)

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
```text
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

### Comparing ****DataFrame with a Series along the column axis:

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")


let data = [{"Col1": [10, 45, 56, 10]}, {"Col2": [23, 20, 10, 24]}]
let df = new dfd.DataFrame(data)
let sf = new dfd.Series([10,40])

let df_rep = df.ne(sf, axis=1)

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
```text
╔═══╤═══════════════════╤═══════════════════╗
║   │ Col1              │ Col2              ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ false             │ true              ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ true              │ true              ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ true              │ true              ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ false             │ true              ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Comparing ****DataFrame with a DataFrame

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")


let data = [{"Col1": [10, 45, 56, 10]}, {"Col2": [23, 300, 10, 24]}]
let data2 = [{"new_col1": [10, 45, 200, 10]}, {"new_Col2": [230, 200, 110, 24]}]

let df = new dfd.DataFrame(data)
let df2 = new dfd.DataFrame(data2)

let df_rep = df.ne(df2)

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
```text
╔═══╤═══════════════════╤═══════════════════╗
║   │ Col1              │ Col2              ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ false             │ true              ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ false             │ true              ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ true              │ true              ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ false             │ false             ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Comparing ****DataFrame with a JavaScript Array

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [[10, 45, 56, 10], [23, 20, 10, 24]]
let df = new dfd.DataFrame(data)
let val = [10, 40, 30, 20]

let df_rep = df.le(val)

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
```text
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ 0                 │ 1                 │ 2                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ true              │ false             │ false             │ true              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ false             │ true              │ true              │ false             ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

