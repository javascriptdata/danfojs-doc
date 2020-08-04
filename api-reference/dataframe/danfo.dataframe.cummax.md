---
description: Return cumulative maximum over a DataFrame or Series axis.
---

# DataFrame.cummax

Returns a DataFrame or Series of the same size containing the cumulative minimum.

**parameter**: {kwargs} {axis: \[int\]}

                  **return**: {DataFrame}



```javascript
let data = [[2, 1, 2, 3], [3, 4, 11, 9], [5, 6, 7, 8]]
let column = ["A", "B", "C", "D"]
let df = new DataFrame(data, { columns: column })
let rslt = [[2, 1, 2, 3], [5, 5, 13, 12], [10, 11, 20, 20]]
df.cummax()
```

