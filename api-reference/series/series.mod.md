---
description: 'Return Modulo of series and other, element-wise (binary operator mod).'
---

# Series.mod

Return Modulo of series and other, element-wise \(binary operator mod\).

Equivalent to series % other

            **parameter:** {other} Series, Number

            **return:** Series

**Example**

```javascript
let data1 = [2, 30, 4, 5]
let data2 = [1.1, 2.2, 3.3, 2.4]
let sf1 = new Series(data1)
let sf2 = new Series(data2)
sf1.mod(sf2)
```

