---
description: Return a random sample of items from an axis of object.
---

# Series.sample

Gets \[num\] number of random rows in a Series

            **parameter:** {rows}  Number of rows to return

            **return:** Series

**Example**

```javascript
let data = [1, 2, 3, 4, 5, 620, 30, 40, 39, 89, 78]
let sf = new Series(data)
sf.sample(2)
```



