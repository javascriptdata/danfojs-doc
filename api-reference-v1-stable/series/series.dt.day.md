---
description: Obtain the numerical representation of the week day.
---

# Series.dt.day

> danfo.Series.dt.**day**()    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/timeseries.js#L216)]

**Parameters**: None

**Returns:** Series (int elements)

**Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = new dfd.date_range({"start":'2016-12-31', "end":'2018-01-08'})
let sf = new dfd.Series(data)

sf.dt.day().print()
```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

```
╔═══╤═══╗
║ 0 │ 6 ║
╟───┼───╢
║ 1 │ 0 ║
╟───┼───╢
║ 2 │ 1 ║
╟───┼───╢
║ 3 │ 2 ║
╟───┼───╢
║ 4 │ 3 ║
╟───┼───╢
║ 5 │ 4 ║
╟───┼───╢
║ 6 │ 5 ║
╟───┼───╢
║ 7 │ 6 ║
╟───┼───╢
║ 8 │ 0 ║
╟───┼───╢
║ 9 │ 1 ║
╚═══╧═══╝
```
