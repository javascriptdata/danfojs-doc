---
description: Group DataFrame using a mapper or by a Series of columns.
---

# DataFrame.groupby

danfo.DataFrame.**groupby**(columns)

| Parameters | Type  | Description                                           | Default |
| ---------- | ----- | ----------------------------------------------------- | ------- |
| columns    | Array | The names of a column(s) in the DataFrame to group by |         |

## **Examples**

## **Groupby a single column from a DataFrame**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [["Pear", 2, 3], ["Pear", 5, 6], ["Apple", 30, 40], ["Apple", 89, 78]]
let cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
let group_df = df.groupby(["A"])
console.log(group_df)
```

```
// ouput
Groupby {
  colDict: {
    Pear: { A: [Array], B: [Array], C: [Array] },
    Apple: { A: [Array], B: [Array], C: [Array] }
  },
  keyToValue: { Pear: [ 'Pear' ], Apple: [ 'Apple' ] },
  keyCol: [ 'A' ],
  data: [
    [ 'Pear', 2, 3 ],
    [ 'Pear', 5, 6 ],
    [ 'Apple', 30, 40 ],
    [ 'Apple', 89, 78 ]
  ],
  columnName: [ 'A', 'B', 'C' ],
  colDtype: [ 'string' ],
  colIndex: [ 0 ]
}
```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

A groupby operation will return a GroupBy class object. You can apply any of the following operation on the groupby result:

1. [count](danfo.dataframe.count.md)
2. [sum](danfo.dataframe.sum.md)
3. [std](danfo.dataframe.std.md)
4. [var](danfo.dataframe.var.md)
5. [mean](danfo.dataframe.mean.md)
6. [cumSum](danfo.dataframe.cumsum.md)
7. [cumMax](danfo.dataframe.cummax.md)
8. [cumProd](danfo.dataframe.cumprod.md)
9. [cumMin](danfo.dataframe.cummin.md)
10. [max](danfo.dataframe.max.md)
11. [min](danfo.dataframe.min.md)

## Example of Groupby and apply a sum function

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [["Pear", 2, 3], ["Pear", 5, 6], ["Apple", 30, 40], ["Apple", 89, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })
let group_df = df.groupby(["A"]).sum()

group_df.print()
```
{% endtab %}
{% endtabs %}

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B_sum             │ C_sum             ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ Pear              │ 7                 │ 9                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ Apple             │ 119               │ 118               ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

## **Groupby a two columns from a DataFrame**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [["Pear", 2, 3], ["Pear", 2, 6], ["Apple", 30, 40], ["Apple", 89, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })
let group_df = df.groupby(["A", "B"]).sum()

group_df.print()
```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C_sum             ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ Pear              │ 2                 │ 9                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ Apple             │ 30                │ 40                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ Apple             │ 89                │ 78                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
