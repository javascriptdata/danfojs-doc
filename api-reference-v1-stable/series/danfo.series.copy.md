# danfo.Series.copy

Make a new copy of Series



**parameter:** 

            **return:** {Series}

**Example**

```javascript
let sf = new Series([30.21091, 40.190901, 3.564, 5.0212])
sf_copy = sf.copy()


let sf = new Series([30.21091, 40.190901, 3.564, 5.0212])
sf = sf.set_index({ "index": ["a", "b", "c", "d"] })
sf_copy = sf.copy()
```

