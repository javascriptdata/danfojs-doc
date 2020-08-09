---
description: Obtain the year in a date time series
---

# Series.dt.year

> danfo.Series.dt.**year**\(\)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/timeseries.js#L228)\]

**Parameters**: None

**Returns:** Series \(int elements\)

**Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = new dfd.date_range({"start":"2000-01-01", period:3, freq:"Y"})
let sf = new dfd.Series(data)
sf.print()
sf.dt.year().print()
```
{% endtab %}
{% endtabs %}

```text
//print date time series
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 1/1/2000, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 1 │ 1/1/2001, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 2 │ 1/1/2002, 1:00:00 AM ║
╚═══╧══════════════════════╝

//print the year series
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 2000                 ║
╟───┼──────────────────────╢
║ 1 │ 2001                 ║
╟───┼──────────────────────╢
║ 2 │ 2002                 ║
╚═══╧══════════════════════╝
```

