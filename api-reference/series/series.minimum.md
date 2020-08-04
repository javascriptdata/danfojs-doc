# Series.minimum



Return minimum of series and other, element-wise \(binary operator div\).



            **parameter:** {other} Series, Numbers to check minimum against

            **return:** {Series}

**Example**

```javascript
let data1 = [30, 40, 3, 5]
let data2 = [10, 41, 2]
let sf1 = new Series(data1)
let sf2 = new Series(data2)
sf1.minimum(sf2)
```

