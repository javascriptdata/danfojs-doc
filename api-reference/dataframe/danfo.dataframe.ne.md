# DataFrame.ne

Get Not equal to of dataframe and other, element-wise \(binary operator ne\).

            **parameter:** {other} DataFrame, Series, Scalar

            **return:** {DataFrame}

**Example1**

```javascript
let data1 = [[10, 45, 56, 10], [25, 23, 20, 10]]
let data2 = [[100, 450, 590, 5], [25, 2, 0, 10]]

let df = new DataFrame(data1)
let df2 = new DataFrame(data2)
let expected = [[true, true, true, true], [false, true, true, false]]
df.ne(df2).values
```

**Examples2**

```javascript
let data1 = [[10, 45, 56, 10], [25, 23, 30, 10]]
let sf = new DataFrame(data1)
let expected = [[true, true, true, true], [true, true, false, true]]
sf.ne(30).values
```

