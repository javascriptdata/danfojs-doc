# danfo.Series.set\_index



Generate a new Series with the specified index. Set the Series index \(row labels\) using an array of the same length.



**parameter:** {kwargs} {index: Array of new index values}

            **return:** {Series}

**Example**

```javascript
let data = [{ alpha: "A", count: 1 }, { alpha: "B", count: 2 }, { alpha: "C", count: 3 }]
let df = new Series(data)
let df_new = df.set_index({ "index": ["one", "two", "three"] })
df_new 


let data = [{ alpha: "A", count: 1 }, { alpha: "B", count: 2 }, { alpha: "C", count: 3 }]
let df = new Series(data)
let df_new = df.set_index({ "index": ["one", "two", "three"] })
df_new 
```

