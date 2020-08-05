# DataFrame.apply

Apply a function along an axis of the DataFrame.

            **parameter:** {kwargs} kargs is defined as {axis: 0 or 1, callable: \[FUNCTION\]

            **return:** Array

**Example1**

```javascript
let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new DataFrame(data, { columns: cols })
let rslt = [64, 126, 127]

let apply_rslt = df.apply({
                axis: 1, callable: (x) => {
                  return x.sum()
                }
```

**Examples2**

```javascript
let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new DataFrame(data, { columns: cols })

let rslt = [6, 15, 90, 206]
let apply_rslt = df.apply({
                axis: 0, callable: (x) => {
                    return x.sum()
                }
```

