---
description: Return the integer indices that would sort the Series values
---

# Series.argSort

> danfo.Series.argSort(options)&#x20;

| Parameters | Type   | Description                            | Default                                              |
| ---------- | ------ | -------------------------------------- | ---------------------------------------------------- |
| options    | Object | **ascending**: How to sort the indices | <p>{<br><strong>ascending</strong>: true</p><p>}</p> |

**Returns:** Series (int element)

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [10, 45, 20, 10, 23, 20, 30, 11]
let sf = new dfd.Series(data)

sf.argSort().print() //defaults to ascending order
sf.argSort({ ascending: false }).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤═══╗
║ 0 │ 3 ║
╟───┼───╢
║ 1 │ 0 ║
╟───┼───╢
║ 2 │ 7 ║
╟───┼───╢
║ 3 │ 5 ║
╟───┼───╢
║ 4 │ 2 ║
╟───┼───╢
║ 5 │ 4 ║
╟───┼───╢
║ 6 │ 6 ║
╟───┼───╢
║ 7 │ 1 ║
╚═══╧═══╝

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
