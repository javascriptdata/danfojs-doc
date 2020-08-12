---
description: Return a random sample of items from an axis of object.
---

# Series.sample

> danfo.Series.sample\(num\)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L98)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| num | Int | number of random samples to obtain | 5 |

**Returns:** Series

**Example**

```javascript
const dfd = require("danfojs")

let data1 = [1, 2, 3, 4, 5, 620, 30, 40, 39, 89, 78]
let sf1 = new dfd.Series(data1)

sf1.sample(5).print()
```

{% tabs %}
{% tab title="Output" %}
```javascript
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 4 │ 39                   ║
╟───┼──────────────────────╢
║ 7 │ 89                   ║
╟───┼──────────────────────╢
║ 0 │ 78                   ║
╟───┼──────────────────────╢
║ 1 │ 620                  ║
╟───┼──────────────────────╢
║ 5 │ 4                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

