---
description: Obtain the column(s) per groups
---

# Groupby.col

> danfo.Groupby.col\(col\_names\)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/groupby.js#L104)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| col\_names | Array | List of column |  |

Returns: Groupby Data structure

Note:    This is similar to pandas `df.groupby(["column"])["col_names"]`

**Examples**

Obtain a column

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data ={'A': ['foo', 'bar', 'foo', 'bar',
                'foo', 'bar', 'foo', 'foo'],
           'B': ['one', 'one', 'two', 'three',
                'two', 'two', 'one', 'three'],
           'C': [1,3,2,4,5,2,6,7],
           'D': [3,2,4,1,5,6,7,8]
        }

let df = new dfd.DataFrame(data)


let grp = df.groupby(["A"])
grp.col(["C"])

//for more coumns
grp.col(["C","D"])
```
{% endtab %}
{% endtabs %}

Apparently the output are not that useful unless you perform some operations like max\(\), count\(\) and the likes. 

```text
//it returns the groupby data structure
GroupBy {
  key_col: [ 'A' ],
  col_dict: {
    foo: [ [Array], [Array], [Array], [Array], [Array] ],
    bar: [ [Array], [Array], [Array] ]
  },
  data: [
    [ 'foo', 'one', 1, 3 ],
    [ 'bar', 'one', 3, 2 ],
    [ 'foo', 'two', 2, 4 ],
    [ 'bar', 'three', 4, 1 ],
    [ 'foo', 'two', 5, 5 ],
    [ 'bar', 'two', 2, 6 ],
    [ 'foo', 'one', 6, 7 ],
    [ 'foo', 'three', 7, 8 ]
  ],
  column_name: [ 'A', 'B', 'C', 'D' ],
  data_tensors: {
    foo: DataFrame {
      kwargs: [Object],
      series: false,
      data: [Array],
      row_data_tensor: [Tensor],
      index_arr: [Array],
      columns: [Array],
      col_data: [Array],
      col_data_tensor: [Tensor],
      col_types: [Array],
      A: [Getter/Setter],
      B: [Getter/Setter],
      C: [Getter/Setter],
      D: [Getter/Setter]
    },
    bar: DataFrame {
      kwargs: [Object],
      series: false,
      data: [Array],
      row_data_tensor: [Tensor],
      index_arr: [Array],
      columns: [Array],
      col_data: [Array],
      col_data_tensor: [Tensor],
      col_types: [Array],
      A: [Getter/Setter],
      B: [Getter/Setter],
      C: [Getter/Setter],
      D: [Getter/Setter]
    }
  },
  group_col_name: [ 'C' ],
  group_col: { foo: [ [Series] ], bar: [ [Series] ] }
}
```



