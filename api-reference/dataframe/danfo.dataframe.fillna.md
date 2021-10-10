---
description: >-
  Fill NaN/undefined values using the specified method. Detect missing values
  for an array-like object.
---

# DataFrame.fillna

danfo.DataFrame.**fillna**(kwargs) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L1235)]

| Parameters | Type   | Description                                                                                                                                                                                                                                                                                                        | Default |
| ---------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------- |
| kwargs     | Object | <p>{<strong>columns</strong>:Array of column name(s) to fill. If undefined fill all columns</p><p><strong>values</strong>: Array | Scalar of value(s) to fill with. </p><p><strong>inplace</strong>: boolean. true | false. Whether to perform operation to the original Object or create a new one. </p><p> }</p> |         |

**Returns:**

**       **return** DataFrame**

## **Examples**

### Fill NaNs in specified columns with specified values 

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"Name":["Apples", "Mango", "Banana", undefined],
            "Count": [NaN, 5, NaN, 10], 
            "Price": [200, 300, 40, 250]}
            
let df = new dfd.DataFrame(data)
df.print()

let df_filled = df.fillna({columns: ["Name", "Count"], values: ["Apples", df["Count"].mean()]})
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

let data = {"Name":["Apples", "Mango", "Banana", undefined],
            "Count": [NaN, 5, NaN, 10], 
            "Price": [200, 300, 40, 250]}

let df = new dfd.DataFrame(data)
let df_filled = df.fillna({ values: ["Apples"] })

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
df.fillna({
    columns: ["Name", "Count"],
    values: ["Apples", df["Count"].mean()],
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
