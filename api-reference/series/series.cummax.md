---
description: Returns cumulative maximum over a series
---

# Series.cummax

> danfo.Series.**cummax**\(\)       \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L825)\]

**Parameters:** None

**Return**: Series

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf1 = new dfd.Series(data1)

sf1.cummax().print()
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
║ 1 │ 45                   ║
╟───┼──────────────────────╢
║ 2 │ 56                   ║
╟───┼──────────────────────╢
║ 3 │ 56                   ║
╟───┼──────────────────────╢
║ 4 │ 56                   ║
╟───┼──────────────────────╢
║ 5 │ 56                   ║
╟───┼──────────────────────╢
║ 6 │ 56                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

