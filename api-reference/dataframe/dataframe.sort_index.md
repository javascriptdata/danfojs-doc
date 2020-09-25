---
description: Sort DataFrame by index
---

# DataFrame.sort\_index

danfo.DataFrame.**sort\_index**\(kwargs\) \[[source](https://github.com/opensource9ja/danfojs/blob/2696f1d8420dd364464aae7c5c175c6cd0ef4c93/danfojs/src/core/frame.js#L2059)\]

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
        <p>{</p>
        <p><b>ascending</b>: Order of sorting</p>
        <p><b>inplace</b>: specify whether to perform the operation to the row/column
          with/without creating a new DataFrame</p>
        <p>}</p>
      </td>
      <td style="text-align:left">{<b>ascending</b>: true, <b>inplace:</b>false}</td>
    </tr>
  </tbody>
</table>

**Returns:**

       ****return **DataFrame**

## **Examples**

### **Sort DataFrame by a column in ascending order**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [[0, 2, 4, "b"],
            [360, 180, 360, "a"],
            [2, 4, 6, "c"]]

let df = new dfd.DataFrame(data, { "columns": ["col1", "col2", "col3", "col4"],
                           index: ["b", "a", "c"] })
df.print()

let df2 = df.sort_index({ ascending: false })
df2.print()
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
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ col1              │ col2              │ col3              │ col4              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ b │ 0                 │ 2                 │ 4                 │ b                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ a │ 360               │ 180               │ 360               │ a                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ c │ 2                 │ 4                 │ 6                 │ c                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝


 //after sorting in descending order

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ col1              │ col2              │ col3              │ col4              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ c │ 2                 │ 4                 │ 6                 │ c                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ b │ 0                 │ 2                 │ 4                 │ b                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ a │ 360               │ 180               │ 360               │ a                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

\*\*\*\*

