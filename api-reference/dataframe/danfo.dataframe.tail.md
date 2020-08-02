---
description: >-
  This function returns last n rows from the object based on position. It is
  useful for quickly verifying data, for example, after sorting or appending
  rows.
---

# danfo.DataFrame.tail

For negative values of n, this function returns all rows except the first n rows, equivalent to `df[n:]`.

**parameter:** {rows}

            **return:** same type as caller

                         The last n rows of the caller object.

```javascript
let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new DataFrame(data, { columns: cols })
```

