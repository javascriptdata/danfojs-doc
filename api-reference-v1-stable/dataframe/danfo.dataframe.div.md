---
description: >-
  Get Float division of DataFrame and other, element-wise (binary operator
  truediv).
---

# DataFrame.div

danfo.DataFrame.div(other, option) \[[source](https://github.com/opensource9ja/danfojs/blob/fe56860b0a303d218d60ba71dee6abf594401556/danfojs/src/core/frame.js#L347)]

| Parameters | Type                               | Description                                                                                                                                                                                  | Default                      |
| ---------- | ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------- |
| other      | DataFrame, Series, Array or Scalar | Object to add with                                                                                                                                                                           |                              |
| option     | Object                             | <p>{</p><p><strong>axis</strong>: 0 for row, 1 for column.</p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p><p>}</p> | { axis: 1, inplace: false }  |

**Returns:**

**       **return** DataFrame**

## **Examples**

### Division of** scalar with **DataFrame along default axis 1

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    "Col1": [10, 45, 56, 10],
    "Col2": [23, 20, 10, 24]
}
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
```
╔════════════╤═══════════════════╤═══════════════════╗
║            │ Col1              │ Col2              ║
╟────────────┼───────────────────┼───────────────────╢
║ 0          │ 5                 │ 11.5              ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ 22.5              │ 10                ║
╟────────────┼───────────────────┼───────────────────╢
║ 2          │ 28                │ 5                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 3          │ 5                 │ 12                ║
╚════════════╧═══════════════════╧═══════════════════╝

```
{% endtab %}
{% endtabs %}

### Division of**  Series with **DataFrame along axis 0

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

let df_new = df.div(sf, { axis: 1 })

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
║ 0          │ 0.25              │ 0.6000000238418…  ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ 1                 │ 0.4000000059604…  ║
╟────────────┼───────────────────┼───────────────────╢
║ 2          │ 1.25              │ 0                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 3          │ 0.25              │ 0.8000000119209…  ║
╚════════════╧═══════════════════╧═══════════════════╝


```
{% endtab %}
{% endtabs %}

### Division of**  **DataFrame **with** a DataFrame

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
```
╔════════════╤═══════════════════╤═══════════════════╗
║            │ Col1              │ Col2              ║
╟────────────┼───────────────────┼───────────────────╢
║ 0          │ 1                 │ 0.1000000014901…  ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ 0.8000000119209…  │ 0                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 2          │ 0.25              │ 1                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 3          │ 0                 │ 2                 ║
╚════════════╧═══════════════════╧═══════════════════╝


```
{% endtab %}
{% endtabs %}

### Division of** ** Array **with** DataFrame along axis 0

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

let df_new = df.div(val, { axis: 0 })

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
║ 0          │ 5                 │ 11.5              ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ 22.5              │ 10                ║
╟────────────┼───────────────────┼───────────────────╢
║ 2          │ 28                │ 5                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 3          │ 5                 │ 12                ║
╚════════════╧═══════════════════╧═══════════════════╝

```
{% endtab %}
{% endtabs %}

### Division works inplace

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

df.div(val, { axis: 0, inplace: true })

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
║ 0          │ 5                 │ 11.5              ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ 22.5              │ 10                ║
╟────────────┼───────────────────┼───────────────────╢
║ 2          │ 28                │ 5                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 3          │ 5                 │ 12                ║
╚════════════╧═══════════════════╧═══════════════════╝


```
{% endtab %}
{% endtabs %}

