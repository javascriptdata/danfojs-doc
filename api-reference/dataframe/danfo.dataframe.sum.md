# DataFrame.sum

Return the sum of the values for the requested axis.

            **parameter:** {kwargs} {axis: 0 for row and 1 for column}

            **return:**  {Series}, Sum of values accross axis

**Example1**

```javascript
let data1 = [[30, 40, 3.1],[5, 5, 5.1],[5, 5, 3.2]]
let sf = new DataFrame(data1)

sf.sum().values
```

