---
description: Access a group of rows and columns by label(s) or a boolean array.
---

# danfo.DataFrame.loc

`.loc[]` is primarily label based, but may also be used with a boolean array.

Allowed inputs are:

* A single label, e.g. `5` or `'a'`, \(note that `5` is interpreted as a _label_ of the index, and **never** as an integer position along the index\).
* A list or array of labels, e.g. `['a', 'b', 'c']`.
* A slice object with labels, e.g. `'a':'f'`.

**parameter:** kwargs object {rows: Array of index, columns: Array of column name\(s\)}

            **return:** DataFrame data structure

```javascript
let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new DataFrame(data, { columns: cols })
let col_df = df.loc({ "rows": ["0:2"], "columns": ["B:C"] })
```



```javascript
let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new DataFrame(data, { columns: cols })
let col_df = df.loc({ "rows": [0, 1], "columns": ["A:C"] })
```

