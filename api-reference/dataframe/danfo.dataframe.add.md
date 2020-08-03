---
description: 'Get Addition of DataFrame and other, element-wise (binary operator add).'
---

# danfo.DataFrame.add

Equivalent to `dataframe + other`, but with support to substitute a fill\_value for missing data in one of the inputs. With reverse version, radd.

Among flexible wrappers \(add, sub, mul, div, mod, pow\) to arithmetic operators: +, -, \*, /, //, %, \*\*.

**parameter:** {other} DataFrame, Series, Array or Number to add

                  **return:** {DataFrame}

```javascript
let data = [[0, 2, 4], [360, 180, 360]]
let df = new DataFrame(data)
df.add(2)
```





