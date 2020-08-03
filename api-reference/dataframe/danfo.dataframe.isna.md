# danfo.DataFrame.isna

Detect missing values for an array-like object.

            **parameter:** 

            **return:** DataFrame

**Example1**

```javascript
let data = [[NaN, 1, 2, 3], [3, 4, undefined, 9], [5, 6, 7, 8]]
let column = ["A", "B", "C", "D"]
let df = new DataFrame(data, { columns: column })
df.isna().values
```

