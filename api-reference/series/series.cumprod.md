---
description: Return the cumulative product of a series
---

# Series.cumprod

> danfo.Series.**cumprod**\(\)       \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L834)\]

**Parameters:** None

**Return**: Series

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf1 = new dfd.Series(data1)

sf1.cumprod().print()
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
║ 1 │ 450                  ║
╟───┼──────────────────────╢
║ 2 │ 25200                ║
╟───┼──────────────────────╢
║ 3 │ 630000               ║
╟───┼──────────────────────╢
║ 4 │ 14490000             ║
╟───┼──────────────────────╢
║ 5 │ 289800000            ║
╟───┼──────────────────────╢
║ 6 │ 2898000000           ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

