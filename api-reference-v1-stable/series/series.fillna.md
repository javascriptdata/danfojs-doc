---
description: Replace all NaN value with specified value
---

# Series.fillna

> danfo.Series.**fillna**(options)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L470)]

| Parameters | Type   | Description                                                                                                                                                                                        | Default                               |
| ---------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------- |
| options    | Object | <p><strong>value</strong>: The value to replace all missing value with. </p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p> | <p>{</p><p>inplace: false</p><p>}</p> |

**Examples**

### Fill nan value and then return new series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [NaN, 1, 2, 33, 4, NaN, 5, 6, 7, 8]
let sf = new dfd.Series(data1)

let sf_rep = sf.fillna({ value: -999})

sf_rep.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
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

### Fill nan value in-place

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [NaN, 1, 2, 33, 4, NaN, 5, 6, 7, 8]
let sf = new dfd.Series(data1)
sf.fillna({ value: -999, inplace: true })

sf.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
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
