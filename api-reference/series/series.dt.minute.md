---
description: Obtain the minutes in a Time Series
---

# Series.dt.minutes

> danfo.Series.dt.**minutes**()  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/timeseries.js#L292)]

**Parameters**: None

**Returns: **Series (int Elements)

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = new dfd.date_range({"start":"2000-01-01", period:3, freq:"m"})
let sf = new dfd.Series(data)
//print the series
sf.print()
//print the minutes series
sf.dt.minutes().print()
```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 1/1/2000, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 1 │ 1/1/2000, 1:01:00 AM ║
╟───┼──────────────────────╢
║ 2 │ 1/1/2000, 1:02:00 AM ║
╚═══╧══════════════════════╝

//print the minutes series
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 0                    ║
╟───┼──────────────────────╢
║ 1 │ 1                    ║
╟───┼──────────────────────╢
║ 2 │ 2                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
