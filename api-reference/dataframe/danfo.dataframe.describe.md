---
description: Generate descriptive statistics.
---

# DataFrame.describe

Descriptive statistics include those that summarize the central tendency, dispersion and shape of a dataset’s distribution, excluding `NaN` values. Analyzes both numeric and object series, as well as `DataFrame` column sets of mixed data types. The output will vary depending on what is provided. Refer to the notes below for more detail.

**parameter**: 

                  **return**: {Series}



```javascript
let data = [[0, 2, 4, "a"],[360, 180, 360, "b"],[2, 4, 6, "c"]]
let df = new DataFrame(data)
let res = [[3, 3, 3], [120.666664, 62, 123.333336],[207.271159, 102.19589, 204.961785],
            [0, 2, 4], [2, 4, 6],
            [360, 180, 360],
            [42961.333333, 10444, 42009.333333]]

df.describe()
```

