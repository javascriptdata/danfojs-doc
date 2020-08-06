---
description: Obtain the day of the month
---

# Series.dt.monthday

> danfo.Series.dt.**monthday**\(\)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/timeseries.js#L268)\]

**Parameters:** None

**Returns**: Series \(Int elements\)

**Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = new dfd.date_range({"start":"2000-01-01", period:4, freq:"D"})
let sf = new dfd.Series(data)
//print series
sf.print()
//print monthdays
sf.dt.monthday().print()
```
{% endtab %}

{% tab title="Browser" %}
```

```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 1/1/2000, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 1 │ 1/2/2000, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 2 │ 1/3/2000, 1:00:00 AM ║
╚═══╧══════════════════════╝

//print monthdays
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 1                    ║
╟───┼──────────────────────╢
║ 1 │ 2                    ║
╟───┼──────────────────────╢
║ 2 │ 3                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

