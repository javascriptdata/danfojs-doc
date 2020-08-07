---
description: Replace values given in replace param with value
---

# Series.replace

> danfo.Series.**replace**\(kwargs\)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L892)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| kwargs\["**replace**"\] | int \| String\| bool | value to be replaced |  |
| kwargs\["**with**"\] | int \| String \| bool | value to replace the previous value |  |
| kwargs\["**inplace**"\] | Bool | mutate the series or create the new series | false |

**Returns**: Series

**Examples**

Replace a value in a series and return a new series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf = new dfd.Series(data1)
let sf_rep = sf.replace({ replace: 10, with: -50 })

sf_rep.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ -50                  ║
╟───┼──────────────────────╢
║ 1 │ 45                   ║
╟───┼──────────────────────╢
║ 2 │ 56                   ║
╟───┼──────────────────────╢
║ 3 │ 25                   ║
╟───┼──────────────────────╢
║ 4 │ 23                   ║
╟───┼──────────────────────╢
║ 5 │ 20                   ║
╟───┼──────────────────────╢
║ 6 │ -50                  ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

Replace a value in a series , with out returning a new series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf = new dfd.Series(data1)
sf.replace({ replace: 10, with: -50, inplace:true })

sf.print()
```
{% endtab %}
{% endtabs %}

```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ -50                  ║
╟───┼──────────────────────╢
║ 1 │ 45                   ║
╟───┼──────────────────────╢
║ 2 │ 56                   ║
╟───┼──────────────────────╢
║ 3 │ 25                   ║
╟───┼──────────────────────╢
║ 4 │ 23                   ║
╟───┼──────────────────────╢
║ 5 │ 20                   ║
╟───┼──────────────────────╢
║ 6 │ -50                  ║
╚═══╧══════════════════════╝
```

