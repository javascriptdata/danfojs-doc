---
description: Returns the absolute value in a Series
---

# Series.abs

> danfo.Series.**abs**(options)&#x20;

| Parameters | Type   | Description                                                                                         | Default                               |
| ---------- | ------ | --------------------------------------------------------------------------------------------------- | ------------------------------------- |
| options    | Object | **inplace**: Boolean indicating whether to perform the operation in-place or not. Defaults to false | <p>{</p><p>inplace: false</p><p>}</p> |

**Returns:** Series

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [-10, 45, 56, -25, 23, -20, 10]
let sf = new dfd.Series(data1)

sf.abs().print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤════╗
║ 0 │ 10 ║
╟───┼────╢
║ 1 │ 45 ║
╟───┼────╢
║ 2 │ 56 ║
╟───┼────╢
║ 3 │ 25 ║
╟───┼────╢
║ 4 │ 23 ║
╟───┼────╢
║ 5 │ 20 ║
╟───┼────╢
║ 6 │ 10 ║
╚═══╧════╝
```
{% endtab %}
{% endtabs %}
