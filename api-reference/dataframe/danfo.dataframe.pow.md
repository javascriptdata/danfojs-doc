---
description: >-
  Get Exponential power of dataframe and other, element-wise (binary operator
  pow).
---

# DataFrame.pow

Equivalent to `dataframe ** other`, but with support to substitute a fill\_value for missing data in one of the inputs. With reverse version, rpow.

Among flexible wrappers \(add, sub, mul, div, mod, pow\) to arithmetic operators: +, -, \*, /, //, %, \*\*.

**parameter**: {other} DataFrame, Series, Array or Number to add

                  **return**: {DataFrame}



```javascript
let data = [[0, 2, 4], [360, 180, 360]]
let df = new DataFrame(data)
df.pow(2)
```



```javascript
let data = [[0, 2, 4], [360, 180, 360]]
let sf = new Series([1, 2, 1])
let df = new DataFrame(data)
df.pow(sf)
```

