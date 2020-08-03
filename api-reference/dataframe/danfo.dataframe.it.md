# danfo.DataFrame.It

Get Less than of dataframe and other, element-wise \(binary operator lt\).

            **parameter:** {other} DataFrame, Series, Scalar

            **return:** {DataFrame}

**Example1**

```javascript
let data1 = [[10, 45, 56, 10], [25, 23, 20, 10]]
let data2 = [[100, 450, 590, 5], [25, 2, 0, 10]]

let df = new DataFrame(data1)
let df2 = new DataFrame(data2)
let expected = [[true, true, true, false],[false, false, false, false]]
df.lt(df2).values
```

**Examples2**

```javascript
let data1 = [[10, 45, 56, 10], [25, 23, 20, 10]]
let sf = new DataFrame(data1)
let expected = [[true, false, false, true],[true, true, true, true]]
sf.lt(30).values
```

