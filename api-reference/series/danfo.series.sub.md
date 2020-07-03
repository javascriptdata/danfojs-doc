---
description: 'Return Subtraction of series and other, element-wise (binary operator sub).'
---

# danfo.Series.sub

Returns the subtraction between a series and other, element-wise \(binary operator subtraction\).

Equivalent to series - other

            **parameter:** {other} Series, Number to subtract

            **return:** Series

**Example**

```javascript
let data1 = [30, 40, 39, 1, 2, 1]
let data2 = [1, 2, 3, 4, 5, 6]
let sf1 = new Series(data1)
let sf2 = new Series(data2)
sf1.sub(sf2)
```

