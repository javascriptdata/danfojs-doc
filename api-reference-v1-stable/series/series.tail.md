---
description: Prints the last n values in a Series
---

# Series.tail

> danfo.Series.tail\(rows\)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L76)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| rows | Int | number of last n values | 5 |

 **Return:** Series

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [1, 2, 3, 4, 5, 620, 30, 40, 39, 89, 78]
let sf1 = new dfd.Series(data1)

sf1.tail().print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔════╤══════════════════════╗
║    │ 0                    ║
╟────┼──────────────────────╢
║ 6  │ 30                   ║
╟────┼──────────────────────╢
║ 7  │ 40                   ║
╟────┼──────────────────────╢
║ 8  │ 39                   ║
╟────┼──────────────────────╢
║ 9  │ 89                   ║
╟────┼──────────────────────╢
║ 10 │ 78                   ║
╚════╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

