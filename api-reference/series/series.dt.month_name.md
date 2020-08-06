---
description: obtain the month name in a Time Series
---

# Series.dt.month\_name

> danfo.Series.dt.month\_name\(\)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/timeseries.js#L241)\]

**Parameters**: None

**Returns:** Series \(String elements\)

**Examples**

{% tabs %}
{% tab title="Output" %}
```javascript
const dfd = require("danfojs")

let data = ["06-30-02019 00:00:12", "07-29-2019 00:30:40", "08-28-2019 00:12:04"]
let sf = new dfd.Series(data)
sf.dt.month_name().print()
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
║ 0 │ Jun                  ║
╟───┼──────────────────────╢
║ 1 │ Jul                  ║
╟───┼──────────────────────╢
║ 2 │ Aug                  ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

