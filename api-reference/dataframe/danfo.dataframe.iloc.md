---
description: Purely integer-location based indexing for selection by position.
---

# danfo.DataFrame.iloc

`.iloc[]` is primarily integer position based \(from `0` to `length-1` of the axis\), but may also be used with a boolean array.

Allowed inputs are:

* An integer, e.g. `5`.
* A list or array of integers, e.g. `[4, 3, 0]`.
* A slice object with ints, e.g. `1:7`.
* A boolean array.
* A `callable` function with one argument \(the calling Series or DataFrame\) and that returns valid output for indexing \(one of the above\). This is useful in method chains, when you don’t have a reference to the calling object, but would like to base your selection on some value.

`.iloc` will raise `IndexError` if a requested indexer is out-of-bounds, except _slice_ indexers which allow out-of-bounds indexing \(this conforms with python/numpy _slice_ semantics\).

**parameter:** kwargs object {rows: Array of index, columns: Array of column index}

            **return:** DataFrame data stucture



```javascript
let data = [[1, 2, 3], [4, 5, 6]]
let cols = ["A", "B", "C"]
let df = new DataFrame(data, { columns: cols })
let col_df = df.iloc({ "rows": [0, 1], "columns": [1, 2] })
let col_data = [[2, 3], [5, 6]]
```

