---
description: Count the number of occurrence for each element in a Series
---

# Series.value\_counts

> danfo.Series.value\_counts()     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L750)]

**Parameters:** None

**Returns:** Series (int element)

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [1, 2, 3, 4, 5, 6, 7, 8, 1, 1, 22, 8, 5, 5, 5]
let sf = new dfd.Series(data1)

sf.value_counts().print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔════╤══════════════════════╗
║    │ 0                    ║
╟────┼──────────────────────╢
║ 1  │ 3                    ║
╟────┼──────────────────────╢
║ 2  │ 1                    ║
╟────┼──────────────────────╢
║ 3  │ 1                    ║
╟────┼──────────────────────╢
║ 4  │ 1                    ║
╟────┼──────────────────────╢
║ 5  │ 4                    ║
╟────┼──────────────────────╢
║ 6  │ 1                    ║
╟────┼──────────────────────╢
║ 7  │ 1                    ║
╟────┼──────────────────────╢
║ 8  │ 2                    ║
╟────┼──────────────────────╢
║ 22 │ 1                    ║
╚════╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
