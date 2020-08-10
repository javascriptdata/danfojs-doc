---
description: Return a cumulative sum of a series
---

# Series.cumsum

> danfo.Series.**cumsum**\(\)       \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L807)\]

**Parameters:** None

**Return**: Series

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")


let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf1 = new dfd.Series(data1)

sf1.cumsum().print()
```
{% endtab %}
{% endtabs %}

```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 10                   ║
╟───┼──────────────────────╢
║ 1 │ 55                   ║
╟───┼──────────────────────╢
║ 2 │ 111                  ║
╟───┼──────────────────────╢
║ 3 │ 136                  ║
╟───┼──────────────────────╢
║ 4 │ 159                  ║
╟───┼──────────────────────╢
║ 5 │ 179                  ║
╟───┼──────────────────────╢
║ 6 │ 189                  ║
╚═══╧══════════════════════╝
```

