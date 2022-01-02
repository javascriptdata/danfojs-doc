---
description: Return the integer indices that would sort the Series values
---

# Series.argsort

> danfo.Series.**argsort**(options)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L965\\)]

| Parameters | Type   | Description                            | Default                                               |
| ---------- | ------ | -------------------------------------- | ----------------------------------------------------- |
| options    | Object | **ascending**: How to sort the indices | <p>{ <br><strong>ascending</strong>: true</p><p>}</p> |

**Returns:** Series (int element)

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [10, 45, 20, 10, 23, 20, 30, 11]
let sf = new dfd.Series(data)

sf.argsort().print() //defaults to ascending order
sf.argsort({ ascending: false }).print()

```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
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

//sorted in descending order
╔═══╤═══╗
║ 0 │ 1 ║
╟───┼───╢
║ 1 │ 6 ║
╟───┼───╢
║ 2 │ 4 ║
╟───┼───╢
║ 3 │ 2 ║
╟───┼───╢
║ 4 │ 5 ║
╟───┼───╢
║ 5 │ 7 ║
╟───┼───╢
║ 6 │ 0 ║
╟───┼───╢
║ 7 │ 3 ║
╚═══╧═══╝
```
{% endtab %}
{% endtabs %}
