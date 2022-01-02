# danfo.Series.sort\_values



Sort a Series in ascending or descending order by some criterion.



 **parameter:** {kwargs} Object, {ascending \(Bool\): Whether to return sorted values in ascending order or not, inplace \(Bool\): Whether to perform sorting on the original Series or not}

            **return:** {Number}

**Example**

```javascript
let sf = new Series([20, 30, 1, 2, 4, 57, 89, 0, 4])
sf.sort_values()


let sf = new Series([20, 30, 1, 2, 4, 57, 89, 0, 4])
sf.sort_values({ "inplace": true })


let sf = new Series([20, 30, 1, 2, 4, 57, 89, 0, 4])
sf.sort_values({ "ascending": false, "inplace": true })
```

