---
description: 'Remove missing values (NaNs, undefined) for DataFrame'
---

# DataFrame.dropna

danfo.DataFrame.**dropna**\(kwargs\) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L1430)\]

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
        <p>{<b>axis</b>: <em>0<b>: </b>Apply along</em> row/index axis</p>
        <p><em><b>             </b>1</em>: Apply across columns axis</p>
        <p><b>inplace</b>:If true, perform operation inplace</p>
        <p>and return None.</p>
        <p>}</p>
      </td>
      <td style="text-align:left">
        <p>{<b>axis</b>: 0,</p>
        <p> <b>inplace: </b>false}</p>
      </td>
    </tr>
  </tbody>
</table>

**Returns:**

       ****return **DataFrame**

## **Examples**

### Drop rows \(axis=0\) with missing values  

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [[1, 2, 3], [NaN, 5, 6], [NaN, 30, 40], [39, undefined, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

df.print()

let df_drop = df.dropna({axis: 0})
df_drop.print()
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
║ 0 │ 1                 │ 2                 │ 3                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Drop columns \(axis=1\) with missing values  

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [[1, 2, 3], [NaN, 5, 6], [NaN, 30, 40], [39, undefined, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

df.print()

df.dropna({axis: 1, inplace: true})
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
```text
╔═══╤═══════════════════╗
║   │ C                 ║
╟───┼───────────────────╢
║ 0 │ 3                 ║
╟───┼───────────────────╢
║ 1 │ 6                 ║
╟───┼───────────────────╢
║ 2 │ 40                ║
╟───┼───────────────────╢
║ 3 │ 78                ║
╚═══╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

