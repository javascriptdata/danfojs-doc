# DataFrame.query

Query the columns of a DataFrame with a boolean expression.

            **parameter:** {kwargs {column: coumn name\[string\], operator: string, value: string\| int}

            **return:**  New DataFrame

**Example1**

```javascript
let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new DataFrame(data, { columns: cols })
let query_df = df.query({ "column": "B", "operator": ">=", "value": 5 })
query_df.values
```

