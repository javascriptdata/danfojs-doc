---
description: Obtain the hours in a time series
---

# Series.dt.hours

> danfo.Series.dt.**hours**()&#x20;

**Parameters:** None

**Returns:** Series (int elements)

**Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = new dfd.dateRange({"start":"2000-01-01", period:3, freq:"H"})
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
```
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
