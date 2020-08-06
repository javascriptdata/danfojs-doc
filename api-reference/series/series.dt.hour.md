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
const dfd = require("danfojs")

let data = ["06-30-02019 02:00:12", "07-29-2019 21:30:40", "08-28-2019 19:12:04"]
let sf = new dfd.Series(data)
sf.dt.hour().print()
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
║ 0 │ 2                    ║
╟───┼──────────────────────╢
║ 1 │ 21                   ║
╟───┼──────────────────────╢
║ 2 │ 19                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

