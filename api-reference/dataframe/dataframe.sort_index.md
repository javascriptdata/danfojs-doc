---
description: Sort DataFrame by index
---

# DataFrame.sortIndex

DataFrame.sortIndex(options) \[[source](https://github.com/opensource9ja/danfojs/blob/e25010c26d9c423412613d820015a48ad03d5c6d/danfojs-node/src/core/frame.js#L2094)]

| Parameters | Type   | Description                                                                                                                                                                             | Default                                      |
| ---------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------- |
| options    | Object | <p>{</p><p><strong>ascending</strong>: Sorting order.</p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p><p>}</p> | {**ascending**: true, \*\*inplace:\*\*false} |

**Returns:**

\*\*\*\* return **DataFrame**

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

let df2 = df.sortIndex({ ascending: false })
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
```
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

***
