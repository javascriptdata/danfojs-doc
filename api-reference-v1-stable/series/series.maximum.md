---
description: Obtain the maximum number between two series
---

# Series.maximum

> danfo.Series.maximum\(other\)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L363)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| other | Series | series to match |  |

**Return:** {Series}

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [30, 40, 3, 5]
let data2 = [10, 41, 2, 0]
let sf1 = new dfd.Series(data1)
let sf2 = new dfd.Series(data2)
sf1.maximum(sf2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 30                   ║
╟───┼──────────────────────╢
║ 1 │ 41                   ║
╟───┼──────────────────────╢
║ 2 │ 3                    ║
╟───┼──────────────────────╢
║ 3 │ 5                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}



