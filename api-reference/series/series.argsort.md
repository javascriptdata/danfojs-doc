---
description: Return the integer indices that would sort the Series values
---

# Series.argsort

> danfo.Series.**argsort**\(ascending\)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L965\)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| ascending | boolean | How to sort the indices. either **True** or **False** | true |

**Returns:**  Series \(int element\)

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [10, 45, 20, 10, 23, 20, 30, 11]
let sf = new dfd.Series(data)

sf.argsort().print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 0                    ║
╟───┼──────────────────────╢
║ 1 │ 3                    ║
╟───┼──────────────────────╢
║ 2 │ 7                    ║
╟───┼──────────────────────╢
║ 3 │ 2                    ║
╟───┼──────────────────────╢
║ 4 │ 5                    ║
╟───┼──────────────────────╢
║ 5 │ 4                    ║
╟───┼──────────────────────╢
║ 6 │ 6                    ║
╟───┼──────────────────────╢
║ 7 │ 1                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

