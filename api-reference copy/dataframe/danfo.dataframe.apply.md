---
description: Apply a function to each element or along a specified axis of a DataFrame.
---

# DataFrame.apply

danfo.DataFrame.**apply**(callable, options) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L1566)]

| Parameters | Type     | Description                                                           | Default   |
| ---------- | -------- | --------------------------------------------------------------------- | --------- |
| callable   | Function | Function to apply to each column or row                               |           |
| options    | Object   | **axis**: 0 or 1. If 0, compute the power column-wise, if 1, row-wise | {axis: 1} |

**Returns:**

&#x20;      ****       return **DataFrame**

## **Examples**

### Apply a  function along default axis 1 (columns)

{% hint style="info" %}
Note that the specified function passed to `apply` will be called with an array of the values across the specified axis.
{% endhint %}

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

function sum_vals(col) {
    return col.reduce((a, b) => a + b, 0);
}

let df_new = df.apply(sum_vals, { axis: 1 })
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
╔═══╤═════╗
║ A │ 64  ║
╟───┼─────╢
║ B │ 126 ║
╟───┼─────╢
║ C │ 127 ║
╚═══╧═════╝
```
{% endtab %}
{% endtabs %}

### Apply a  function along  axis 0 (row)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

function sum_vals(col) {
    return col.reduce((a, b) => a + b, 0);
}

let df_new = df.apply(sum_vals, { axis: 0 })
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
╔═══╤═════╗
║ 0 │ 6   ║
╟───┼─────╢
║ 1 │ 15  ║
╟───┼─────╢
║ 2 │ 90  ║
╟───┼─────╢
║ 3 │ 206 ║
╚═══╧═════╝

```
{% endtab %}
{% endtabs %}
