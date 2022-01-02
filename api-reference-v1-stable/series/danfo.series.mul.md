---
description: 'Return Multiplication of series and other, element-wise (binary operator mul).'
---

# danfo.Series.mul

Return Multiplication of series and other, element-wise \(binary operator mul\).

Equivalent to series \* other, but with support to substitute a fill\_value for missing data in one of the inputs.

            **parameter:** {Series, Number to multiply with.

            **return:** Series

**Example**

```javascript
let data1 = [30, 40, 3, 5]
let data2 = [1, 2, 3, 4]
let sf1 = new Series(data1)
let sf2 = new Series(data2)
sf1.mul(sf2)
```



