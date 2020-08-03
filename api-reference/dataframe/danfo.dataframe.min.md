---
description: Return the minimum of the values for the requested axis.
---

# danfo.DataFrame.min

If you want the _index_ of the minimum, use `idxmin`. This is the equivalent of the `numpy.ndarray` method `argmin`.

**parameter**: {axis} Number {0: row, 1 : column} Axis for the function to be applied on

                  **return**: {Series}



```javascript
let data = [[0, 2, 4], [360, 180, 360]]
let df = new DataFrame(data)
df.min()
```



```javascript
let data = [[0, 2, 4], [360, 180, 360]]
let df = new DataFrame(data)
df.min({ "axis": 0 })
```

