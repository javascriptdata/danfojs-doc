---
description: >-
  Get Exponential power of dataframe and other, element-wise (binary operator
  pow).
---

# DataFrame.pow

danfo.DataFrame.pow(other, option) \[[source](https://github.com/opensource9ja/danfojs/blob/fe56860b0a303d218d60ba71dee6abf594401556/danfojs/src/core/frame.js#L347)]

| Parameters | Type                               | Description                                                                                                                                                                                  | Default                      |
| ---------- | ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------- |
| other      | DataFrame, Series, Array or Scalar | Object to add with                                                                                                                                                                           |                              |
| option     | Object                             | <p>{</p><p><strong>axis</strong>: 0 for row, 1 for column.</p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p><p>}</p> | { axis: 1, inplace: false }  |

**Returns:**

&#x20;      ****       return **DataFrame**

## **Examples**

### Exponential of **scalar with** DataFrame along default axis 1

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    "Col1": [10, 45, 56, 10],
    "Col2": [23, 20, 10, 24]
}
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
```
╔════════════╤═══════════════════╤═══════════════════╗
║            │ Col1              │ Col2              ║
╟────────────┼───────────────────┼───────────────────╢
║ 0          │ 100               │ 529               ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ 2025              │ 400               ║
╟────────────┼───────────────────┼───────────────────╢
║ 2          │ 3136              │ 100               ║
╟────────────┼───────────────────┼───────────────────╢
║ 3          │ 100               │ 576               ║
╚════════════╧═══════════════════╧═══════════════════╝



```
{% endtab %}
{% endtabs %}

### Exponential of  **Series with** DataFrame along axis 0

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

let df_new = df.pow(sf, { axis: 1 })

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
║ 0          │ 1                 │ 243               ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ 256               │ 32                ║
╟────────────┼───────────────────┼───────────────────╢
║ 2          │ 625               │ 0                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 3          │ 1                 │ 1024              ║
╚════════════╧═══════════════════╧═══════════════════╝



```
{% endtab %}
{% endtabs %}

### Exponential of  ****  DataFrame with a DataFrame

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
```
╔════════════╤═══════════════════╤═══════════════════╗
║            │ Col1              │ Col2              ║
╟────────────┼───────────────────┼───────────────────╢
║ 0          │ 1                 │ 1048576           ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ 1024              │ 0                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 2          │ 95367433551872    │ 1                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 3          │ 0                 │ 16                ║
╚════════════╧═══════════════════╧═══════════════════╝



```
{% endtab %}
{% endtabs %}

### Exponential of **** Array with DataFrame along axis 0

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

let df_new = df.pow(val, { axis: 0 })

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
║ 0          │ 100               │ 529               ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ 2025              │ 400               ║
╟────────────┼───────────────────┼───────────────────╢
║ 2          │ 3136              │ 100               ║
╟────────────┼───────────────────┼───────────────────╢
║ 3          │ 100               │ 576               ║
╚════════════╧═══════════════════╧═══════════════════╝


```
{% endtab %}
{% endtabs %}

### Exponential works inplace

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

df.pow(val, { axis: 0, inplace: true })

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
║ 0          │ 100               │ 529               ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ 2025              │ 400               ║
╟────────────┼───────────────────┼───────────────────╢
║ 2          │ 3136              │ 100               ║
╟────────────┼───────────────────┼───────────────────╢
║ 3          │ 100               │ 576               ║
╚════════════╧═══════════════════╧═══════════════════╝



```
{% endtab %}
{% endtabs %}

