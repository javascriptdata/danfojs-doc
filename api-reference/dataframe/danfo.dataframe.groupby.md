# DataFrame.groupby

Group DataFrame using a mapper or by a Series of columns.

            **parameter:** {col} col is a list of column with maximum length of two

            **return:**  groups

**Example1**

```javascript
let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new DataFrame(data, { columns: cols })
let group_df = df.groupby(["A"]);

group_df.col_dict
```

