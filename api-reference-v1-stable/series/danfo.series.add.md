---
description: 'Return Addition of series and other, element-wise (binary operator add).'
---

# danfo.Series.add

Return Addition of series and other, element-wise \(binary operator add\).

            **parameter:** {other} Series or Number to add

            **return:** Series

**Example**

```javascript
let data = [1, 2, 3, 4, 5, 6]
let data2 = [30, 40, 39, 1, 2, 1]
let sf = new Series(data)
let sf2 = new Series(data2)
sf.add(sf2)
```

