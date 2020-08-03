---
description: 'Get Modulo of dataframe and other, element-wise (binary operator mod).'
---

# danfo.DataFrame.mod

Equivalent to `dataframe % other`, but with support to substitute a fill\_value for missing data in one of the inputs. With reverse version, rmod.

Among flexible wrappers \(add, sub, mul, div, mod, pow\) to arithmetic operators: +, -, \*, /, //, %, \*\*.

**parameter**: {other} DataFrame, Series, Array or Number to add

                  **return**: {DataFrame}



```javascript
let data = [[0, 2, 4], [360, 180, 360]]
let df = new DataFrame(data)
df.mod(2)
```



```javascript
let data = [[0, 2, 4], [31, 15, 360]]
let sf = new Series([1, 2, 1])
let df = new DataFrame(data)
df.mod(sf)
```

