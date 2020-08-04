# DataFrame.dropna

Remove missing values.

            **parameter:** {kwargs} kwargs \[Object\] {axis: \[int\]{o or 1}, inplace:\[boolean\]}

            **return:** New DataFrame 

**Example1**

```javascript
let data = [[NaN, 1, 2, 3], [3, 4, NaN, 9], [5, 6, 7, 8]]
let column = ["A", "B", "C", "D"]
let df = new DataFrame(data, { columns: column })

df.dropna().values
```

