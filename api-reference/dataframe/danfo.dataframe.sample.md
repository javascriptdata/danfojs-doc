---
description: Return a random sample of items from an axis of object.
---

# DataFrame.sample

You can use random\_state for reproducibility.

**parameter:** {rows}

            **return:** A new object of same type as caller containing n items randomly sampled from the caller object.

```javascript
let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78], [100, 200, 300]]
let cols = ["A", "B", "C"]
let df = new DataFrame(data, { columns: cols })
df.sample(2)
```



