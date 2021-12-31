---
description: >-
  Fill NaN/undefined values using the specified method. Detect missing values
  for an array-like object.
---

# DataFrame.fillna

danfo.DataFrame.**fillna**(values, options) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L1235)]

| Parameters | Type            | Description                                                                                                                                                                                                                      | Default          |
| ---------- | --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------- |
| values     | Array \| Scalar | The list of value(s) to use for replacement.                                                                                                                                                                                     |                  |
| options    | Object          | <p>{<strong>columns</strong>:Array of column name(s) to fill. If undefined fill all columns </p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false </p><p> }</p> | {inplace: false} |

**Returns:**

**       **return** DataFrame**

## **Examples**

### Fill missing values in specified columns with specified values 

Missing values are NaN, undefined or null values

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    "Name": ["Apples", "Mango", "Banana", undefined],
    "Count": [NaN, 5, NaN, 10],
    "Price": [200, 300, 40, 250]
}

let df = new dfd.DataFrame(data)
df.print()

let updateValues = ["Apples", df["Count"].mean()]
let df_filled = df.fillna({ columns: ["Name", "Count"], values: updateValues })
df_filled.print()

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
//Before filling
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ Apples            │ NaN               │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ Banana            │ NaN               │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ NaN               │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


 //After filling

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ Apples            │ 7.5               │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ Banana            │ 7.5               │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ Apples            │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝═╝
```
{% endtab %}
{% endtabs %}

### Fill all columns with NaNs with a specified value 

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    "Name": ["Apples", "Mango", "Banana", undefined],
    "Count": [NaN, 5, NaN, 10],
    "Price": [200, 300, 40, 250]
}

let df = new dfd.DataFrame(data)
let df_filled = df.fillna("Apples")

df_filled.print()

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

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ Apples            │ Apples            │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ Banana            │ Apples            │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ Apples            │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Fill NaNs inplace 

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
let data = {
    "Name": ["Apples", "Mango", "Banana", undefined],
    "Count": [NaN, 5, NaN, 10],
    "Price": [200, 300, 40, 250]
}

let df = new dfd.DataFrame(data)
let values = ["Apples", df["Count"].mean()]
df.fillna(values, {
    columns: ["Name", "Count"],
    inplace: true
})
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

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ Apples            │ Apples            │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ Banana            │ Apples            │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ Apples            │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
