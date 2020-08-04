# DataFrame.column

Return the elements of the specified column in the dataframe

            **parameter:** col\_name: the name of a column in the database.

            **return:**  tensor of shape 1

**Example1**

```javascript
let data = [{ alpha: "A", count: 1 }, { alpha: "B", count: 2 }, { alpha: "C", count: 3 }]
let options = { columns: ["Gender", "count"] }
let df = new DataFrame(data, options)
let col_data = df.column("count")

col_data.values
```

