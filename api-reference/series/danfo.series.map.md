# danfo.Series.map



map all the element in a column to a variable



**parameter:** {{callable} callable can either be a funtion or an object

            **return:** {array}

**Example**

```javascript
let sf = new Series([1, 2, 3, 4])
let map = { 1: "ok", 2: "okie", 3: "frit", 4: "gop" }
sf.map(map)



let sf = new Series([1, 2, 3, 4])
let func_map = (x) => {
    return x + 1
}
sf.map(func_map)
```

