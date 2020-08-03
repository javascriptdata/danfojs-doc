# danfo.DataFrame.concat

Concatenate pandas objects along a particular axis with optional set logic along the other axes.

            **parameter:** kwargs { df\_list: \[Array of DataFrame\], axis: int}

            **return:** DataFrame object

**Example1**

```javascript
let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new DataFrame(data, { columns: cols })

let data1 = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols1 = ["A", "B", "C"]
let df1 = new DataFrame(data1, { columns: cols1 })

let data2 = [[1, 2, 3, 5], [4, 5, 6, 8], [20, 30, 40, 10]]
let cols2 = ["A", "B", "C", "D"]
let df2 = new DataFrame(data2, { columns: cols2 })

let new_df = DataFrame.concat({ "df_list": [df, df1, df2], "axis": 0 })

new_df.values
```

**Examples2**

```javascript
let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new DataFrame(data, { columns: cols })

let data1 = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols1 = ["A", "B", "C"]
let df1 = new DataFrame(data1, { columns: cols1 })

let data2 = [[1, 2, 3, 5], [4, 5, 6, 8], [20, 30, 40, 10]]


let cols2 = ["A", "B", "C", "D"]
let df2 = new DataFrame(data2, { columns: cols2 })

let new_df = DataFrame.concat({ "df_list": [df, df1, df2], "axis": 1 })

new_df.values
```

