---
description: >-
  This function returns the first n rows for the object based on position. It is
  useful for quickly testing if your object has the right type of data in it.
---

# danfo.DataFrame.head

For negative values of n, this function returns all rows except the last n rows, equivalent to `df[:-n]`.

**parameter:** {rows}

            **return:** same type as caller

                         The first n rows of the caller object.

```javascript
let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new DataFrame(data, { columns: cols })
```

```javascript
let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new DataFrame(data, { columns: cols })
```



