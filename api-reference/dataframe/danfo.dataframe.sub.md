---
description: Get Subtraction of dataframe and other, element-wise (binary operator sub).
---

# DataFrame.sub

danfo.DataFrame.sub(other, option) \[[source](https://github.com/opensource9ja/danfojs/blob/fe56860b0a303d218d60ba71dee6abf594401556/danfojs/src/core/frame.js#L347)]

| Parameters | Type                               | Description                                                                                                                                                                                  | Default                      |
| ---------- | ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------- |
| other      | DataFrame, Series, Array or Scalar | Object to add with                                                                                                                                                                           |                              |
| option     | Object                             | <p>{</p><p><strong>axis</strong>: 0 for row, 1 for column.</p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p><p>}</p> | { axis: 1, inplace: false }  |

**Returns:**

**       **return** DataFrame**

## **Examples**

### Subtraction of** scalar to **DataFrame along default axis 1

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    "Col1": [10, 45, 56, 10],
    "Col2": [23, 20, 10, 24]
}
let df = new dfd.DataFrame(data)

let df_new = df.sub(2)

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
```
╔════════════╤═══════════════════╤═══════════════════╗
║            │ Col1              │ Col2              ║
╟────────────┼───────────────────┼───────────────────╢
║ 0          │ 8                 │ 21                ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ 43                │ 18                ║
╟────────────┼───────────────────┼───────────────────╢
║ 2          │ 54                │ 8                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 3          │ 8                 │ 22                ║
╚════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Subtraction of**  Series to **DataFrame along axis 0

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    "Col1": [1, 4, 5, 1],
    "Col2": [3, 2, 0, 4]
}

let df = new dfd.DataFrame(data)
let sf = new dfd.Series([4, 5])

let df_new = df.sub(sf, { axis: 1 })

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
```
╔════════════╤═══════════════════╤═══════════════════╗
║            │ Col1              │ Col2              ║
╟────────────┼───────────────────┼───────────────────╢
║ 0          │ -3                │ -2                ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ 0                 │ -3                ║
╟────────────┼───────────────────┼───────────────────╢
║ 2          │ 1                 │ -5                ║
╟────────────┼───────────────────┼───────────────────╢
║ 3          │ -3                │ -1                ║
╚════════════╧═══════════════════╧═══════════════════╝

```
{% endtab %}
{% endtabs %}

### Subtraction of**  **DataFrame to a DataFrame

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = {"Col1": [1, 4, 5, 0], 
            "Col2": [2, 0, 1, 4]}
            
let data2 = {"new_col1": [1, 5, 20, 10],
             "new_Col2": [20, 2, 1, 2]}

let df = new dfd.DataFrame(data)
let df2 = new dfd.DataFrame(data2)

let df_new = df.sub(df2)

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
```
╔════════════╤═══════════════════╤═══════════════════╗
║            │ Col1              │ Col2              ║
╟────────────┼───────────────────┼───────────────────╢
║ 0          │ 0                 │ -18               ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ -1                │ -2                ║
╟────────────┼───────────────────┼───────────────────╢
║ 2          │ -15               │ 0                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 3          │ -10               │ 2                 ║
╚════════════╧═══════════════════╧═══════════════════╝

```
{% endtab %}
{% endtabs %}

### Subtraction of** ** Array to DataFrame along axis 0

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    "Col1": [10, 45, 56, 10],
    "Col2": [23, 20, 10, 24]
}

let df = new dfd.DataFrame(data)
let val = [2, 2, 2, 2]

let df_new = df.sub(val, { axis: 0 })

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
```
╔════════════╤═══════════════════╤═══════════════════╗
║            │ Col1              │ Col2              ║
╟────────────┼───────────────────┼───────────────────╢
║ 0          │ 8                 │ 21                ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ 43                │ 18                ║
╟────────────┼───────────────────┼───────────────────╢
║ 2          │ 54                │ 8                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 3          │ 8                 │ 22                ║
╚════════════╧═══════════════════╧═══════════════════╝


```
{% endtab %}
{% endtabs %}

### Subtraction works inplace

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    "Col1": [10, 45, 56, 10],
    "Col2": [23, 20, 10, 24]
}

let df = new dfd.DataFrame(data)
let val = [2, 2, 2, 2]

df.sub(val, { axis: 0, inplace: true })

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
╔════════════╤═══════════════════╤═══════════════════╗
║            │ Col1              │ Col2              ║
╟────────────┼───────────────────┼───────────────────╢
║ 0          │ 8                 │ 21                ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ 43                │ 18                ║
╟────────────┼───────────────────┼───────────────────╢
║ 2          │ 54                │ 8                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 3          │ 8                 │ 22                ║
╚════════════╧═══════════════════╧═══════════════════╝


```
{% endtab %}
{% endtabs %}

