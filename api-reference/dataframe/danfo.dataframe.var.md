---
description: Return unbiased variance over requested axis.
---

# DataFrame.var

Normalized by N-1 by default. This can be changed using the ddof argument

**parameter**: {axis} Number {0: row, 1 : column} Axis for the function to be applied on

                  **return**: {Series}



```javascript
let data = [[0, 2, 4], [360, 180, 360]]
let df = new DataFrame(data)
df.var()
```



```javascript
let data = [[0, 2, 4], [360, 180, 360]]
let df = new DataFrame(data)
df.var(0) 
```

