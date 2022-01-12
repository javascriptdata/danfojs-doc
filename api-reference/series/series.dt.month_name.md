---
description: obtain the month name in a Time Series
---

# Series.dt.monthName

> danfo.Series.dt.monthName() \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/timeseries.js#L241)]

**Parameters**: None

**Returns:** Series (String elements)

**Examples**

{% tabs %}
{% tab title="Output" %}
```javascript
const dfd = require("danfojs-node")

let data = new dfd.date_range({"start":'2018-01', freq:'M', period:3})
let sf = new dfd.Series(data)
//print series
sf.print()
//print month names
sf.dt.monthName().print()
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
║ 0 │ 1/1/2018, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 1 │ 2/1/2018, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 2 │ 3/1/2018, 1:00:00 AM ║
╚═══╧══════════════════════╝

╔═══╤═════╗
║ 0 │ Jan ║
╟───┼─────╢
║ 1 │ Feb ║
╟───┼─────╢
║ 2 │ Mar ║
╚═══╧═════╝
```
{% endtab %}
{% endtabs %}
