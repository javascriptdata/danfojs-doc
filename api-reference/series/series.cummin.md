---
description: Returns the cumulative min of a Series
---

# Series.cumMin

> danfo.Series.**cumMin**(options)&#x20;

| Parameters | Type   | Description                                                    | Default                                                |
| ---------- | ------ | -------------------------------------------------------------- | ------------------------------------------------------ |
| options    | Object | **inplace**: Whether to perform the operation in-place or not. | <p>{</p><p><strong>inplace</strong>: false</p><p>}</p> |

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


let data1 = [10, 45, 56, 5, 23, 20, 10]
let sf1 = new dfd.Series(data1)

sf1.cumMin().print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤════╗
║ 0 │ 10 ║
╟───┼────╢
║ 1 │ 10 ║
╟───┼────╢
║ 2 │ 10 ║
╟───┼────╢
║ 3 │ 5  ║
╟───┼────╢
║ 4 │ 5  ║
╟───┼────╢
║ 5 │ 5  ║
╟───┼────╢
║ 6 │ 5  ║
╚═══╧════╝
```
{% endtab %}
{% endtabs %}
