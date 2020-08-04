# DataFrame.addColumn

Add column to an existing dataframe

            **parameter:** {kwargs} Object keys\[columns \[string\] and value\[Array\]\]

            **return:**  DataFrame

**Example1**

```javascript
let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new DataFrame(data, { columns: cols })

let new_col = [1, 2, 3, 4]

df.addColumn({ "column": "D", "value": new_col });

df.values
```

