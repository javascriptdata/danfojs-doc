---
description: >-
  Drop specified labels from rows or columns.Remove rows or columns by
  specifying label names and corresponding axis.
---

# DataFrame.drop

danfo.DataFrame.**drop**\(kwargs\) \[[source](https://github.com/opensource9ja/danfojs/blob/cf5c7ae3a009458e61eedd18d9c9b5b6b10d5276/danfojs/src/core/frame.js#L125)\]

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
        <p><b>columns</b>: [Array(Columns| Index)] array of column names to drop</p>
        <p><b>index</b>: [Array(Columns| Index)] index labels to drop</p>
        <p><b>axis</b>: row=0, columns=1</p>
        <p><b>inplace</b>: specify whether to drop the row/column with/without creating
          a new DataFrame</p>
        <p>}</p>
      </td>
      <td style="text-align:left">{<b>axis</b>: 1, <b>inplace:</b>false}</td>
    </tr>
  </tbody>
</table>

**Returns:**

       ****return **DataFrame**

## **Examples**

### Drop columns by specifying the names

By setting **inplace** to _true_, the original DataFrame is modified and nothing is returned. To not modify the original DataFrame and return a new one, set **inplace** to false or leave it as default.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20, 30, 47.3, -20],
             "B": [34, -4, 5, 6] ,
             "C": [20, 20, 30, 30],
             "D": ["a", "b", "c", "c"] }

let df = new dfd.DataFrame(data)
df.drop({ columns: ["C", "B"], axis: 1, inplace: true });
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
╔═══╤═══════════════════╤═══════════════════╗
║   │ A                 │ D                 ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ -20               │ a                 ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 30                │ b                 ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 47.3              │ c                 ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ -20               │ c                 ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Drop rows by specifying int labels/index

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20, 30, 47.3, -20],
             "B": [34, -4, 5, 6] ,
             "C": [20, 20, 30, 30],
             "D": ["a", "b", "c", "c"] }

let df = new dfd.DataFrame(data)
df.drop({ index: [0, 2], axis: 0, inplace: true });
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
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 30                │ -4                │ 20                │ b                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ -20               │ 6                 │ 30                │ c                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Drop rows by specifying string labels/index

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20, 30, 47.3, -20],
             "B": [34, -4, 5, 6] ,
             "C": [20, 20, 30, 30],
             "D": ["a", "b", "c", "c"] }

let df = new dfd.DataFrame(data, {index: ["a", "b", "c", "d"]})
df.drop({ index: ["a", "c"], axis: 0, inplace: true });
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
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ b │ 30                │ -4                │ 20                │ b                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ d │ -20               │ 6                 │ 30                │ c                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
