---
description: Assign new Index to Series
---

# danfo.Series.set\_index

> danfo.series.**set\_index\(**kwargs**\)** \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L614)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| kwargs | Object {} | The object contains the key **index** and assigned an array value of equal length to the Series. format {"index": \[Array\] } |   |

**Example**

```javascript
const dfd = require("danfojs")

let data = [{ alpha: "A", count: 1 }, { alpha: "B", count: 2 }, { alpha: "C", count: 3 }]
let df = new dfd.Series(data)
let df_new = df.set_index({ "index": ["one", "two", "three"] })
df_new.print()
```

**OUTPUT**

![](../../.gitbook/assets/series.reset_index.png)

```javascript
const dfd = require("danfojs")

let data = ["Humans","Life","Meaning","Fact","Truth"]
let df = new dfd.Series(data)
let df_new = df.set_index({ "index": ["H", "L", "M","F","T"] })
df_new.print()
```

**OUTPUT**

![](../../.gitbook/assets/series_reset_index2.png)

