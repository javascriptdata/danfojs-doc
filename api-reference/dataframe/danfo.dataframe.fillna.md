# DataFrame.fillna

Fill NA/NaN values using the specified method.Detect missing values for an array-like object.

            **parameter:** nan\_val

            **return:**  New DataFrame\(data, { columns: columns }\)

**Example1**

```javascript
let data = [[NaN, 1, 2, 3], [3, 4, NaN, 9], [5, 6, 7, 8]]
let column = ["A", "B", "C", "D"]
let df = new DataFrame(data, { columns: column })

df.fillna(-999).values
```

