---
description: Return the median of the values for the requested axis.
---

# danfo.DataFrame.median

**parameter**: {axis} Number {0: row, 1 : column} Axis for the function to be applied on

                  **return**: {Series}

```javascript
let data = [[0, 2, 4], [360, 180, 360]]
let df = new DataFrame(data)
df.median({ "axis": 0 })
```



```javascript
let data = [[0, 2, 4], [360, 180, 360]]
let df = new DataFrame(data)
df.median()
```

