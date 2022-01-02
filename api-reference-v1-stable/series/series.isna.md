---
description: Detect Missing values
---

# Series.isna

> danfo.Series.**isna**\(\)       \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L449)\]

**Parameters**: None

**Returns**:  Series \(Boolean element\)

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [NaN, undefined, "girl", "Man"]
let sf = new dfd.Series(data1)

sf.isna().print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ true                 ║
╟───┼──────────────────────╢
║ 1 │ true                 ║
╟───┼──────────────────────╢
║ 2 │ false                ║
╟───┼──────────────────────╢
║ 3 │ false                ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

