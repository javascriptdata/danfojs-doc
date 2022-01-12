---
description: Obtain the first n rows for the object based on position.
---

# Series.head

> danfo.Series.head(rows)&#x20;

| Parameters | Type | Description              | Default |
| ---------- | ---- | ------------------------ | ------- |
| rows       | Int  | number of first n values | 5       |

**Return:** Series

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [1, 2, 3, 4, 5, 620, 30, 40, 39, 89, 78]
let sf1 = new dfd.Series(data1)

sf1.head().print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
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
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
