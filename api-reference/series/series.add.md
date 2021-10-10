---
description: Return Addition of series and other, element-wise (binary operator add).
---

# Series.add

> danfo.Series.add(other, options)  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L129)]

| Parameters | Type          | Description                                                                                    | Default                               |
| ---------- | ------------- | ---------------------------------------------------------------------------------------------- | ------------------------------------- |
| other      | Series\|int\| | values                                                                                         |                                       |
| options    | Object        | inplace: Boolean indicating whether to perform the operation inplace or not. Defaults to false | <p>{</p><p>inplace: false</p><p>}</p> |

**Return:** Series

**Example**

subtract from values of another series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [30, 40, 3, 5]
let data2 = [1, 2, 3, 4]
let sf1 = new dfd.Series(data1)
let sf2 = new dfd.Series(data2)
sf1.add(sf2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 31                   ║
╟───┼──────────────────────╢
║ 1 │ 42                   ║
╟───┼──────────────────────╢
║ 2 │ 6                    ║
╟───┼──────────────────────╢
║ 3 │ 9                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

subtract from a value

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [1, 2, 3, 4, 5]
let sf1 = new dfd.Series(data1)

sf1.add(2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 3                    ║
╟───┼──────────────────────╢
║ 1 │ 4                    ║
╟───┼──────────────────────╢
║ 2 │ 5                    ║
╟───┼──────────────────────╢
║ 3 │ 6                    ║
╟───┼──────────────────────╢
║ 4 │ 7                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

