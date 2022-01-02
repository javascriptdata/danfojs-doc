---
description: This function returns the first n rows for the object based on position.
---

# danfo.Series.head



Prints the first n values in a Series

            **parameter:** {rows}  Number of rows to return

            **return:** Series

**Example**

```javascript
let data = [1, 2, 3, 4, 5, 620, 30, 40, 39, 89, 78]
let cols = ["A"]
let sf = new Series(data, { columns: cols })
sf.head()
```



