---
description: Add new column to a DataFrame
---

# DataFrame.addColumn

danfo.DataFrame.**addColumn**\(kwargs\) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L1083)\]

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
        <p>{<b>column</b> : str, name of the column to add</p>
        <p><b> value: </b>Array, values to add }</p>
      </td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

**Returns:**

       ****return **Null**

## **Examples**

## **Add new column to DataFrame**

New columns get added at the end of the DataFrame, and this happens  so returns nothing,

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
let data = {"A": [30, 1, 2, 3], 
            "B": [34, 4, 5, 6], 
            "C": [20, 20, 30, 40]}

let df = new dfd.DataFrame(data)
df.print()

let new_col = [1, 2, 3, 4]
df.addColumn({ "column": "D", "value": new_col });

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
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 30                │ 34                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 4                 │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 5                 │ 30                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 3                 │ 6                 │ 40                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


 Shape: (4,3) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 30                │ 34                │ 20                │ 1                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 4                 │ 20                │ 2                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 5                 │ 30                │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 3                 │ 6                 │ 40                │ 4                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

