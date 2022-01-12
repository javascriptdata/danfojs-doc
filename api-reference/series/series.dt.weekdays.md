---
description: Obtain the days of the weeks
---

# Series.dt.dayOfWeek

> danfo.Series.dt.dayOfWeek() \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/timeseries.js#L255)]

**Parameters**: None

**Returns:** Series (String elements)

**Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = new dfd.dateRange({"start":'2016-12-31', "end":'2018-01-08'})
let sf = new dfd.Series(data)
//print series
sf.print()
//print days of the week
sf.dt.dayOfWeek().print()
```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

```
╔═══╤════════════════════════╗
║ 0 │ 12/31/2016, 1:00:00 AM ║
╟───┼────────────────────────╢
║ 1 │ 1/1/2017, 1:00:00 AM   ║
╟───┼────────────────────────╢
║ 2 │ 1/2/2017, 1:00:00 AM   ║
╟───┼────────────────────────╢
║ 3 │ 1/3/2017, 1:00:00 AM   ║
╟───┼────────────────────────╢
║ 4 │ 1/4/2017, 1:00:00 AM   ║
╟───┼────────────────────────╢
║ 5 │ 1/5/2017, 1:00:00 AM   ║
╟───┼────────────────────────╢
║ 6 │ 1/6/2017, 1:00:00 AM   ║
╟───┼────────────────────────╢
║ 7 │ 1/7/2017, 1:00:00 AM   ║
╟───┼────────────────────────╢
║ 8 │ 1/8/2017, 1:00:00 AM   ║
╟───┼────────────────────────╢
║ 9 │ 1/9/2017, 1:00:00 AM   ║
╚═══╧════════════════════════╝

╔═══╤═══╗
║ 0 │ 6 ║
╟───┼───╢
║ 1 │ 0 ║
╟───┼───╢
║ 2 │ 1 ║
╟───┼───╢
║ 3 │ 2 ║
╟───┼───╢
║ 4 │ 3 ║
╟───┼───╢
║ 5 │ 4 ║
╟───┼───╢
║ 6 │ 5 ║
╟───┼───╢
║ 7 │ 6 ║
╟───┼───╢
║ 8 │ 0 ║
╟───┼───╢
║ 9 │ 1 ║
╚═══╧═══╝
```
