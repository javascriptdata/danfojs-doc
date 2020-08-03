---
description: Return the mean of the values for the requested axis.
---

# danfo.DataFrame.mean

**parameter**: {axis} Number {0: row, 1 : column} Axis for the function to be applied on

                  **return**: {Series}



```javascript
let data = [[0, 2, 4], [360, 180, 360]]
let df = new DataFrame(data, { columns: ["col1", "col2", "col3"] })
df.mean()
```

```javascript
let data = [[0, 2, 4], [360, 180, 360]]
let df = new DataFrame(data)
df.mean(0)
```

