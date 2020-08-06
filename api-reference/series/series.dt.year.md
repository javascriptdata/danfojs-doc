---
description: Obtain the year in a date time series
---

# Series.dt.year

> danfo.Series.dt.**year**\(\)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/timeseries.js#L228)\]

**Parameters**: None

**Returns:** Series \(int elements\)

**Examples**

```text
const dfd = require("danfojs")

let data = new dfd.date_range({"start":'2016-7-31', "end":'2016-12-08', freq:"M"})
let sf = new dfd.Series(data)
// sf.print()
sf.dt.month().print()
```

