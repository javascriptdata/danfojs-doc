---
description: Group DataFrame using a mapper or by a Series of columns.
---

# DataFrame.groupby

danfo.DataFrame.**groupby**\(columns\) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L1142)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| columns | Array | The names of a column\(s\) in the DataFrame to group by |  |

**Returns:**

       ****return **DataFrame.groups**

## **Examples**

## **Select a single column from a DataFrame**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new DataFrame(data, { columns: cols })
let group_df = df.groupby(["A"]);

group_df.col_dict
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
║   │ Name                 ║
╟───┼──────────────────────╢
║ 0 │ Apples               ║
╟───┼──────────────────────╢
║ 1 │ Mango                ║
╟───┼──────────────────────╢
║ 2 │ Banana               ║
╟───┼──────────────────────╢
║ 3 │ NaN                  ║
╚═══╧══════════════════════╝

╔═══╤══════════════════════╗
║   │ Name                 ║
╟───┼──────────────────────╢
║ 0 │ Apples               ║
╟───┼──────────────────────╢
║ 1 │ Mango                ║
╟───┼──────────────────────╢
║ 2 │ Banana               ║
╟───┼──────────────────────╢
║ 3 │ NaN                  ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

To select more than one column with specific rows, you can use any of the following: [DataFrame.loc](danfo.dataframe.loc.md), [DataFrame.iloc](danfo.dataframe.iloc.md) or [DataFrame.query](danfo.dataframe.query.md)

