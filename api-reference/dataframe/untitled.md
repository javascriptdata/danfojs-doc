---
description: This function drops a row (axis=0) or column (axis=1) based on the axis.
---

# danfo.DataFrame.drop



Returns 



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

