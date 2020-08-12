---
description: Remove missing values from Series
---

# Series.dropna

> danfo.Series.**dropna**\(kwargs\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L931)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| kwargs\["**inplace**"\] | bool | return a new series or not.  | false |

**Returns**: Series

**Examples**

Drop all nan value and then return New Series.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, undefined, 10, 23, 20, undefined, 10]
let sf = new dfd.Series(data1)
let sf_rep = sf.dropna()

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
║ 0 │ 10                   ║
╟───┼──────────────────────╢
║ 1 │ 45                   ║
╟───┼──────────────────────╢
║ 3 │ 10                   ║
╟───┼──────────────────────╢
║ 4 │ 23                   ║
╟───┼──────────────────────╢
║ 5 │ 20                   ║
╟───┼──────────────────────╢
║ 7 │ 10                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

Drop nan values without returning new series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, undefined, 10, 23, 20, undefined, 10]
let sf = new dfd.Series(data1)
sf.dropna({inplace:true})

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
║ 0 │ 10                   ║
╟───┼──────────────────────╢
║ 1 │ 45                   ║
╟───┼──────────────────────╢
║ 3 │ 10                   ║
╟───┼──────────────────────╢
║ 4 │ 23                   ║
╟───┼──────────────────────╢
║ 5 │ 20                   ║
╟───┼──────────────────────╢
║ 7 │ 10                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

