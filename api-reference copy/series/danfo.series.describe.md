# danfo.Series.describe



Generate descriptive statistics. Descriptive statistics include those that summarize the central tendency, dispersion and shape of a dataset’s distribution, excluding NaN values



**parameter:** 

            **return:** {frame}

**Example**

```javascript
let data = [{ alpha: "A", count: 1 }, { alpha: "B", count: 2 }, { alpha: "C", count: 3 }]
let df = new Series(data)
df.set_index({ "index": ["one", "two", "three"] })


let data = [1,2,3,4,5,6]
let df = new Series(data)
df.set_index({ "index": ["one", "two", "three", "four", "five", "six"], "inplace": true })
df.reset_index()
```

