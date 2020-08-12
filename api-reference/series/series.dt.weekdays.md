---
description: Obtain the days of the weeks
---

# Series.dt.weekdays

> danfo.Series.dt.**weekdays**\(\)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/timeseries.js#L255)\]

**Parameters**: None

**Returns:** Series \(String elements\)

**Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = new dfd.date_range({"start":'2016-12-31', "end":'2017-01-08'})
let sf = new dfd.Series(data)
//print series
sf.print()
//print days of the week
sf.dt.weekdays().print()
```
{% endtab %}

{% tab title="Browser" %}
```

```
{% endtab %}
{% endtabs %}

```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 12/31/2016, 1:00:... ║
╟───┼──────────────────────╢
║ 1 │ 1/1/2017, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 2 │ 1/2/2017, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 3 │ 1/3/2017, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 4 │ 1/4/2017, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 5 │ 1/5/2017, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 6 │ 1/6/2017, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 7 │ 1/7/2017, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 8 │ 1/8/2017, 1:00:00 AM ║
╚═══╧══════════════════════╝

//print days of the week
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ Sat                  ║
╟───┼──────────────────────╢
║ 1 │ Sun                  ║
╟───┼──────────────────────╢
║ 2 │ Mon                  ║
╟───┼──────────────────────╢
║ 3 │ Tue                  ║
╟───┼──────────────────────╢
║ 4 │ Wed                  ║
╟───┼──────────────────────╢
║ 5 │ Thu                  ║
╟───┼──────────────────────╢
║ 6 │ Fri                  ║
╟───┼──────────────────────╢
║ 7 │ Sat                  ║
╟───┼──────────────────────╢
║ 8 │ Sun                  ║
╚═══╧══════════════════════╝
```

