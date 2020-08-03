# danfo.DataFrame.ge

Get Greater than or equal to of dataframe and other, element-wise \(binary operator ge\).

            **parameter:** {other} DataFrame, Series, Scalar

            **return:** {DataFrame}

**Example1**

```javascript
let data1 = [[10, 45, 56, 10], [25, 23, 20, 10]]
let data2 = [[100, 450, 590, 5], [25, 2, 0, 10]]

let df = new DataFrame(data1)
let df2 = new DataFrame(data2)
let expected = [[false, false, false, true], [true, true, true, true]]
df.ge(df2).values
```

**Examples2**

```javascript
 let data1 = [[10, 45, 56, 10], [25, 23, 30, 10]]
 let sf = new DataFrame(data1)
 let expected = [[false, true, true, false], [false, false, true, false]]
 sf.ge(30).values
```

