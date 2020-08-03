# danfo.DataFrame.nanindex

Return the index of NaN index

**parameter:** 

            **return:** Array list \(int\) 

**Example1**

```javascript
let data = [[NaN, 1, 2, 3], [3, 4, NaN, 9], [5, 6, 7, 8]]
let column = ["A", "B", "C", "D"]
let df = new DataFrame(data, { columns: column })

df.nanIndex()
```

