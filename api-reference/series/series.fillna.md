---
description: Replace all NaN value with specified value
---

# Series.fillna

> danfo.Series.**fillna**\(\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L470)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| kwargs\["**value**"\] | int \| String\| bool | value to replace the NaN values |  |
| kwargs\["**inplace**"\] | bool | return a new series or not.  | false |

**Returns:**  Series

**Examples**

Fill nan value and then return new series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [NaN, 1, 2, 33, 4, NaN, 5, 6, 7, 8]
let sf = new dfd.Series(data1)

let sf_rep = sf.fillna({ value: -999})

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
║ 0 │ -999                 ║
╟───┼──────────────────────╢
║ 1 │ 1                    ║
╟───┼──────────────────────╢
║ 2 │ 2                    ║
╟───┼──────────────────────╢
║ 3 │ 33                   ║
╟───┼──────────────────────╢
║ 4 │ 4                    ║
╟───┼──────────────────────╢
║ 5 │ -999                 ║
╟───┼──────────────────────╢
║ 6 │ 5                    ║
╟───┼──────────────────────╢
║ 7 │ 6                    ║
╟───┼──────────────────────╢
║ 8 │ 7                    ║
╟───┼──────────────────────╢
║ 9 │ 8                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

Fill nan value without retutning new Series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [NaN, 1, 2, 33, 4, NaN, 5, 6, 7, 8]
let sf = new dfd.Series(data1)
sf.fillna({ value: -999, inplace: true })

sf.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ -999                 ║
╟───┼──────────────────────╢
║ 1 │ 1                    ║
╟───┼──────────────────────╢
║ 2 │ 2                    ║
╟───┼──────────────────────╢
║ 3 │ 33                   ║
╟───┼──────────────────────╢
║ 4 │ 4                    ║
╟───┼──────────────────────╢
║ 5 │ -999                 ║
╟───┼──────────────────────╢
║ 6 │ 5                    ║
╟───┼──────────────────────╢
║ 7 │ 6                    ║
╟───┼──────────────────────╢
║ 8 │ 7                    ║
╟───┼──────────────────────╢
║ 9 │ 8                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

