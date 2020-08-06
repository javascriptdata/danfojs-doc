---
description: Obtain the seconds in Date series
---

# Series.dt.seconds

> danfo.Series.dt.**seconds**\(\)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/timeseries.js#L280)\]

**Parameters**: None

**Returns:** Series \(Int elements\)

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = ["06-30-02019 00:00:12", "07-29-2019 00:30:40", "08-28-2019 00:12:04"]
let sf = new dfd.Series(data)
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
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 12                   ║
╟───┼──────────────────────╢
║ 1 │ 40                   ║
╟───┼──────────────────────╢
║ 2 │ 4                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

