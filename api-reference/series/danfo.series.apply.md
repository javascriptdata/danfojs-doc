# danfo.Series.apply



The apply function is similar to the map function, just that it only takes in a function



**parameter:** {callable} callable \[FUNCTION\]

            **return:** {array}

**Example**

```javascript
let sf = new Series([1, 2, 3, 4, 5, 6, 7, 8])

let apply_func = (x) => {
    return x + x
}
sf.apply(apply_func)
```

