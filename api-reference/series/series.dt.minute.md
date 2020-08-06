---
description: Obtain the minutes in a Time Series
---

# Series.dt.minutes

> danfo.Series.dt.**minutes**\(\)  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/timeseries.js#L292)\]

**Parameters**: None

**Returns:** Series \(int Elements\)

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = ["06-30-02019 00:00:12", "07-29-2019 00:30:40", "08-28-2019 00:12:04"]
let sf = new dfd.Series(data)
sf.dt.minutes().print()
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
║ 0 │ 0                    ║
╟───┼──────────────────────╢
║ 1 │ 30                   ║
╟───┼──────────────────────╢
║ 2 │ 12                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

