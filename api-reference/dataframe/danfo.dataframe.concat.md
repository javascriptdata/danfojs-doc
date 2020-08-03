# danfo.DataFrame.concat

Merge DataFrame or named Series objects with a database-style join.

            **parameter:** {kwargs} keys: left, right, on, how

            **return:** DataFrame

**Example1**

```javascript
let data = [['K0', 'k0', 'A0', 'B0'], ['k0', 'K1', 'A1', 'B1'],['K1', 'K0', 'A2', 'B2'], ['K2', 'K2', 'A3', 'B3']]
let data2 = [['K0', 'k0', 'C0', 'D0'], ['K1', 'K0', 'C1', 'D1'],['K1', 'K0', 'C2', 'D2'], ['K2', 'K0', 'C3', 'D3']]

let colum1 = ['Key1', 'Key2', 'A', 'B']
let colum2 = ['Key1', 'Key2', 'A', 'D']

let df1 = new DataFrame(data, { columns: colum1 })
let df2 = new DataFrame(data2, { columns: colum2 })
let merge_df = DataFrame.merge({ "left": df1, "right": df2, "on": ["Key1", "Key2"], "how": "outer" })

merge_df.values
```

**Examples2**

```javascript
let data = [['K0', 'k0', 'A0', 'B0'], ['k0', 'K1', 'A1', 'B1'],['K1', 'K0', 'A2', 'B2'], ['K2', 'K2', 'A3', 'B3']]
let data2 = [['K0', 'k0', 'C0', 'D0'], ['K1', 'K0', 'C1', 'D1'],['K1', 'K0', 'C2', 'D2'], ['K2', 'K0', 'C3', 'D3']]

let colum1 = ['Key1', 'Key2', 'A', 'B']
let colum2 = ['Key1', 'Key2', 'A', 'D']

let df1 = new DataFrame(data, { columns: colum1 })
let df2 = new DataFrame(data2, { columns: colum2 })
let merge_df = DataFrame.merge({ "left": df1, "right": df2, "on": ["Key1", "Key2"], "how": "inner" })

merge_df.values
```

