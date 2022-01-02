---
description: Apply a function to a Dataframe values element-wise.
---

# DataFrame.apply\_map

danfo.DataFrame.**apply\_map**(callable, options) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L1566)]

| Parameters | Type     | Description                                                           | Default   |
| ---------- | -------- | --------------------------------------------------------------------- | --------- |
| callable   | Function | Function to apply to each column or row                               |           |
| options    | Object   | **axis**: 0 or 1. If 0, compute the power column-wise, if 1, row-wise | {axis: 1} |

**Returns:**

&#x20;      ****       return **DataFrame**

## **Examples**

### Apply a  function to all values in a DataFrame

{% hint style="info" %}
Note that the specified function passed to `apply` will be called with each element in the DataFrame. If you need to apply a function across an axis, then use the [apply](danfo.dataframe.apply.md) function.&#x20;
{% endhint %}

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    short_name: ["NG", "GH", "EGY", "SA"],
    long_name: ["Nigeria", "Ghana", "Eqypt", "South Africa"]
}
let df = new dfd.DataFrame(data)

function lower(x) {
    return `${x}`.toLowerCase()
}

let df_new = df.apply_map(lower)
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
║            │ short_name        │ long_name         ║
╟────────────┼───────────────────┼───────────────────╢
║ 0          │ ng                │ nigeria           ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ gh                │ ghana             ║
╟────────────┼───────────────────┼───────────────────╢
║ 2          │ egy               │ eqypt             ║
╟────────────┼───────────────────┼───────────────────╢
║ 3          │ sa                │ south africa      ║
╚════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
