---
description: >-
  Return Exponential power of series and other, element-wise (binary operator
  pow).
---

# Series.pow

Return Exponential power of series and other, element-wise \(binary operator pow\).

Equivalent to series \*\* other

            **parameter:** {other} Series, Number to multiply with.

            **return:** Series

**Example**

```javascript
let data1 = [2, 3, 4, 5]
let data2 = [1, 2, 3, 0]
let sf1 = new Series(data1)
let sf2 = new Series(data2)
sf1.pow(sf2)
```

