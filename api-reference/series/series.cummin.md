---
description: Returns the cumulative min of a Series
---

# Series.cummin

> danfo.Series.**cummin**\(\)       \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L816)\]

**Parameters:** None

**Return**: Series

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")


let data1 = [10, 45, 56, 5, 23, 20, 10]
let sf1 = new dfd.Series(data1)

sf1.cummin().print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 10                   ║
╟───┼──────────────────────╢
║ 1 │ 10                   ║
╟───┼──────────────────────╢
║ 2 │ 10                   ║
╟───┼──────────────────────╢
║ 3 │ 5                    ║
╟───┼──────────────────────╢
║ 4 │ 5                    ║
╟───┼──────────────────────╢
║ 5 │ 5                    ║
╟───┼──────────────────────╢
║ 6 │ 5                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

