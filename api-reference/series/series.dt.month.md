---
description: Obtain the month in a date time series
---

# Series.dt.month

> danfo.Series.dt.**month**\(\)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/timeseries.js#L193)\]

**Parameters**: None

**Returns:** Series \(int elements\)

**Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = new dfd.date_range({"start":'2016-7-31', "end":'2016-12-08', freq:"M"})
let sf = new dfd.Series(data)

sf.dt.month().print()
```
{% endtab %}

{% tab title="Browser" %}
```

```
{% endtab %}
{% endtabs %}

```text
╔═══╤════╗
║ 0 │ 6  ║
╟───┼────╢
║ 1 │ 7  ║
╟───┼────╢
║ 2 │ 9  ║
╟───┼────╢
║ 3 │ 9  ║
╟───┼────╢
║ 4 │ 11 ║
╟───┼────╢
║ 5 │ 11 ║
╚═══╧════╝
```

