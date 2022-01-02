---
description: Obtain the seconds in Date series
---

# Series.dt.seconds

> danfo.Series.dt.**seconds**()   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/timeseries.js#L280)]

**Parameters**: None

**Returns:** Series (Int elements)

**Example**

Obtain the seconds of the datetime

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = new dfd.date_range({"start":"2000-01-01", period:3, freq:"s"})
let sf = new dfd.Series(data)
//print the series frame
sf.print()

//print the seconds obtained
sf.dt.seconds().print()
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
║ 0 │ 1/1/2000, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 1 │ 1/1/2000, 1:00:01 AM ║
╟───┼──────────────────────╢
║ 2 │ 1/1/2000, 1:00:02 AM ║
╚═══╧══════════════════════╝

╔═══╤═══╗
║ 0 │ 0 ║
╟───┼───╢
║ 1 │ 1 ║
╟───┼───╢
║ 2 │ 2 ║
╚═══╧═══╝

```
{% endtab %}
{% endtabs %}
