---
description: Makes a deep copy of a Series
---

# Series.copy

> danfo.Series.copy()   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L569)]

**parameter:** 

**Return:** Series

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [30.21091, 40.190901, 3.564, 5.0212]
let sf1 = new dfd.Series(data1)
let sf2 = sf1.copy()

sf2.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 30.21091             ║
╟───┼──────────────────────╢
║ 1 │ 40.190901            ║
╟───┼──────────────────────╢
║ 2 │ 3.564                ║
╟───┼──────────────────────╢
║ 3 │ 5.0212               ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
