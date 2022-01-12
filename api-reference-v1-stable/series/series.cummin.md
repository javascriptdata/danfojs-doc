---
description: Returns the cumulative min of a Series
---

# Series.cummin

> danfo.Series.**cummin**(options) \[[source](https://github.com/opensource9ja/danfojs/blob/e25010c26d9c423412613d820015a48ad03d5c6d/danfojs-node/src/core/series.js#L721)]

| Parameters | Type   | Description                                                     | Default                                                |
| ---------- | ------ | --------------------------------------------------------------- | ------------------------------------------------------ |
| options    | Object | **inplace**: Whether to perform the operation in-place or not.  | <p>{</p><p><strong>inplace</strong>: false</p><p>}</p> |

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


let data1 = [10, 45, 56, 5, 23, 20, 10]
let sf1 = new dfd.Series(data1)

sf1.cummin().print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
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
