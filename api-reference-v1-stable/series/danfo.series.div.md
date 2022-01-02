---
description: >-
  Return Floating division of series and other, element-wise (binary operator
  truediv).
---

# danfo.Series.div

Return division of series and other, element-wise \(binary operator div\).

Equivalent to series / other

            **parameter:** {other} Series, Number to divide with.

            **return:** Series

**Example**

```javascript
let data1 = [30, 40, 3, 5]
let data2 = [1, 2, 3, 4]
let sf1 = new Series(data1)
let sf2 = new Series(data2)
sf1.div(sf2)
```

