---
description: Obtain the unique value in a Series
---

# Series.unique

> danfo.Series.**unique**\(\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L736)\]

**Parameters**: None

**Returns**: Series

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [1, 2, 3, 4, 5, 6, 7, 8, 1, 1, 22, 8, 5, 5, 5]
let sf = new dfd.Series(data1)

sf.unique().print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 1                    ║
╟───┼──────────────────────╢
║ 1 │ 2                    ║
╟───┼──────────────────────╢
║ 2 │ 3                    ║
╟───┼──────────────────────╢
║ 3 │ 4                    ║
╟───┼──────────────────────╢
║ 4 │ 5                    ║
╟───┼──────────────────────╢
║ 5 │ 6                    ║
╟───┼──────────────────────╢
║ 6 │ 7                    ║
╟───┼──────────────────────╢
║ 7 │ 8                    ║
╟───┼──────────────────────╢
║ 8 │ 22                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

