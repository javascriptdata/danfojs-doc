# Series.reset\_index



Generate a new Series with the index reset. This is useful when the index needs to be treated as a column, or when the index is meaningless and needs to be reset to the default before another operation.



**parameter:** {kwargs} {inplace: Modify the Series in place \(do not create a new object, drop: Just reset the index, without inserting it as a column in the new DataFrame.}

            **return:** {Series}

**Example**

```javascript
const dfd = require("danfojs")

let data = [{ alpha: "A", count: 1 }, { alpha: "B", count: 2 }, { alpha: "C", count: 3 }]
let df = new dfd.Series(data)
let df_new = df.set_index({ "index": ["one", "two", "three"] })
let df_reset = df_new.reset_index()
df_reset.print()


let data = [1,2,3,4,5,6]
let df = new Series(data)
df.set_index({ "index": ["one", "two", "three", "four", "five", "six"], "inplace": true })
let df_new = df.reset_index()
df_new 
```

