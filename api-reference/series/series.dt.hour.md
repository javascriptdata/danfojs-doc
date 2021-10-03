---
description: Obtain the hours in a time series
---

# Series.dt.hour

> danfo.Series.dt.**hour**\(\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/timeseries.js#L205)\]

**Parameters:** None

**Returns:** Series \(int elements\)

**Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = new dfd.date_range({"start":"2000-01-01", period:3, freq:"H"})
let sf = new dfd.Series(data)
// print series
sf.print()
// print hour series
sf.dt.hours().print()
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
║ 0 │ 1/1/2000, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 1 │ 1/1/2000, 2:00:00 AM ║
╚═══╧══════════════════════╝

╔═══╤═══╗
║ 0 │ 1 ║
╟───┼───╢
║ 1 │ 2 ║
╚═══╧═══╝

```
{% endtab %}
{% endtabs %}

