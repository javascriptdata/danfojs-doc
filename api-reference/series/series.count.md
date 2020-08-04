---
description: Return the sum of the values in a series.
---

# Series.count

Return number of non-NA/null observations in the Series.

This is equivalent to the method numpy.sum

            **parameter:** 

            **return:** {Number}, sum of values in Series

**Example**

```javascript
let data = ["boy", "gitl", "woman", NaN]
let sf = new Series(data)
sf.count()
```



