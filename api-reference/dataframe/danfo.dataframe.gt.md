# danfo.DataFrame.gt

Get Greater than of dataframe and other, element-wise \(binary operator gt\).

            **parameter:** {other} DataFrame, Series, Scalar

            **return:** {DataFrame}

**Example1**

```javascript
let data1 = [[10, 45, 56, 10], [25, 23, 20, 10]]
let data2 = [[100, 450, 590, 5], [25, 2, 0, 10]]

let df = new DataFrame(data1)
let df2 = new DataFrame(data2)
let expected = [[false, false, false, true], [false, true, true, false]]
df.gt(df2).values
```

**Examples2**

```javascript
let data1 = [[10, 45, 56, 10], [25, 23, 20, 10]]
let sf = new DataFrame(data1)
let expected = [[false, true, true, false], [false, false, false, false]]
assert.deepEqual(sf.gt(30).values, expected)
```

