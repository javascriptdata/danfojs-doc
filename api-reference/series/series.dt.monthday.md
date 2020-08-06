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

let data = ["06-30-02019 00:00:12", "07-29-2019 00:30:40", "08-28-2019 00:12:04"]
let sf = new dfd.Series(data)
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
║ 0 │ 30                   ║
╟───┼──────────────────────╢
║ 1 │ 29                   ║
╟───┼──────────────────────╢
║ 2 │ 28                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

