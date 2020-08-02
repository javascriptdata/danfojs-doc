---
description: Drop specified labels from rows or columns.
---

# danfo.DataFrame.drop

Remove rows or columns by specifying label names and corresponding axis, or by specifying directly index or column names. When using a multi-index, labels on different levels can be removed by specifying the level.

            **parameter:** {kwargs}  Object \(Optional configuration object

                                     **axis**: row=0, columns=1

**parameter:** {callable} callable \[FUNCTION\]

                                     **inplace**: specify whether to drop the row/column with/without creating a new DataFrame}

   **return:** {array}

            **return:** DataFrame without the removed index or column labels.

                         

**Example**

```javascript
let data = [[1, 2, 3], [4, 5, 6]]
let cols = ["A", "B", "C"]
let df = new DataFrame(data, { columns: cols })
df.drop("C", { axis: 1, inplace: true });
```

