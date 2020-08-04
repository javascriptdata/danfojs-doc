---
description: Count non-NA cells for each column or row.
---

# DataFrame.count

The values None, NaN, NaT, and optionally numpy.inf \(depending on pandas.options.mode.use\_inf\_as\_na\) are considered NA.

**parameter**: **axis**{0 or ‘index’, 1 or ‘columns’}, default 0

                  **return**: {Series}



```javascript
let data = [[0, 2, 4], [360, 180.1, 360.11], [NaN, 2, 4], [360, undefined, 360]]
let df = new DataFrame(data)
df.count()
```



```javascript
 let data = [[0, 2, 4, NaN], [360, undefined, 360, 70]]
 let df = new DataFrame(data)
 df.count(0)
```



