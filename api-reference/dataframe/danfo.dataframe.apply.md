---
description: >-
  Apply a function to each element or along a specified axis of a DataFrame.
  Supports JavaScipt functions when axis is not specified, and accepts
  Tensorflow functions when axis is specified.
---

# DataFrame.apply

danfo.DataFrame.**apply**\(kwargs\) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L1566)\]

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameters</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Default</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">kwargs</td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">
        <p>{<b>callable</b>: Function to call on each element,</p>
        <p><b>axis</b>: <em>undefined</em>: if undefined, then any JavaScript function</p>
        <p>is accepted and will be applied element-wise.</p>
        <p><em><b>             </b>0<b>: </b>Apply along</em> row/index axis</p>
        <p><em><b>             </b>1</em>: Apply across columns axis</p>
        <p>}</p>
      </td>
      <td style="text-align:left">undefined</td>
    </tr>
  </tbody>
</table>

**Returns:**

       ****return **DataFrame**

## **Examples**

### Apply a JavaScript function to all elements in DataFrame

The **apply** function calls a JavaScript function on every element of the DataFrame when the axis is not specified.  

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

function sum_vals(x) {
    return x + 20
}

let df_new = df.apply({callable: sum_vals })
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
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 21                │ 22                │ 23                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 24                │ 25                │ 26                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 40                │ 50                │ 60                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 59                │ 109               │ 98                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [{ short_name: ["NG", "GH", "EGY", "SA"] },
             { long_name: ["Nigeria", "Ghana", "Eqypt", "South Africa"] }]
let df = new dfd.DataFrame(data)

function lower(x) {
    return x.toLowerCase()
}

let df_new = df.apply({ callable: lower })
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
║   │ short_name        │ long_name         ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ ng                │ nigeria           ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ gh                │ ghana             ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ egy               │ eqypt             ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ sa                │ south africa      ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Apply [Tensorflow](https://js.tensorflow.org/api/latest/) function element-wise

You can call any compatible [Tensorflow](https://js.tensorflow.org/api/latest/) function on a DataFrame across a specified axis. For functions that operate _**element-wise**_ and returns the same shape as the original DataFrame, you must specify an axis of 0.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

function sum_vals(x) {
    return x.logSigmoid()
}

let df_new = df.apply({axis: 0, callable: sum_vals })
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
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ -0.3132616579...  │ -0.1269280463...  │ -0.0485873296...  ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ -0.0181499607...  │ -0.0067153489...  │ -0.0024756519...  ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ -2.0611536921...  │ -9.3576229122...  │ -4.2483541311...  ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ -1.1548223864...  │ -2.2273639090...  │ -1.3336148713...  ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Apply [Tensorflow](https://js.tensorflow.org/api/latest/) function along column axis

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

function sum_vals(x) {
    return x.sum()
}

let df_new = df.apply({axis: 1, callable: sum_vals })
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
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ A │ 64                   ║
╟───┼──────────────────────╢
║ B │ 126                  ║
╟───┼──────────────────────╢
║ C │ 127                  ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

