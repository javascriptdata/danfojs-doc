---
description: >-
  Set the DataFrame index using existing columns or an array (of the equal
  length).
---

# DataFrame.set\_index

danfo.DataFrame.**set\_index**\(kwargs\) \[[source](https://github.com/opensource9ja/danfojs/blob/cf5c7ae3a009458e61eedd18d9c9b5b6b10d5276/danfojs/src/core/frame.js#L125)\]

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
        <p><b>key</b>: This key can be either a single column name or a single array
          of the same length as the calling DataFrame,</p>
        <p><b>drop</b>: Delete columns to be used as the new index.</p>
        <p><b>inplace</b>: specify whether to perform the operation to the row/column
          with/without creating a new DataFrame</p>
        <p>}</p>
      </td>
      <td style="text-align:left">{<b>drop</b>: true, <b>inplace:</b>false}</td>
    </tr>
  </tbody>
</table>

**Returns:**

       ****return **DataFrame**

## **Examples**

### **Setting index to a column in the DataFrame**

{% tabs %}
{% tab title="Node" %}
```javascript

const dfd = require("danfojs-node")

let data = { "A": [-20, 30, 47.3],
             "B": [34, -4, 5, 6],
             "C": [20, 2, 3, 30] }


let df = new dfd.DataFrame(data, {index: ["a", "b", "a"]})
df.print()

df.set_index({key: "A", inplace: true})
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
║ a │ -20               │ 34                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ b │ 30                │ -4                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ a │ 47.3              │ 5                 │ 30                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


//after setting index

╔══════╤═══════════════════╤═══════════════════╗
║      │ B                 │ C                 ║
╟──────┼───────────────────┼───────────────────╢
║ -20  │ 34                │ 20                ║
╟──────┼───────────────────┼───────────────────╢
║ 30   │ -4                │ 20                ║
╟──────┼───────────────────┼───────────────────╢
║ 47.3 │ 5                 │ 30                ║
╚══════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### **Set index to an array of the same length**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20, 30, 47.3],
             "B": [34, -4, 5, 6],
             "C": [20, 2, 3, 30] }


let df = new dfd.DataFrame(data)
df.print()

let new_index = ["a", "b", "a"]
df.set_index({key: new_index, inplace: true})
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
║ 0 │ -20               │ 34                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 30                │ -4                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 47.3              │ 5                 │ 30                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


 //after setting the index

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ a │ -20               │ 34                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ b │ 30                │ -4                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ a │ 47.3              │ 5                 │ 30                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

**Note:** To reset an index to the default values, use the [DataFrame.reset\_index](dataframe.reset_index.md).
