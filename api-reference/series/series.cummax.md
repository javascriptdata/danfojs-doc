---
description: Returns cumulative maximum over a series
---

# Series.cumMax

> danfo.Series.**cumMax**(options)

| Parameters | Type   | Description                                                    | Default                                                |
| ---------- | ------ | -------------------------------------------------------------- | ------------------------------------------------------ |
| options    | Object | **inplace**: Whether to perform the operation in-place or not. | <p>{</p><p><strong>inplace</strong>: false</p><p>}</p> |

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf1 = new dfd.Series(data1)

sf1.cumMax().print()
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
║ 3 │ 56 ║
╟───┼────╢
║ 4 │ 56 ║
╟───┼────╢
║ 5 │ 56 ║
╟───┼────╢
║ 6 │ 56 ║
╚═══╧════╝
```
{% endtab %}
{% endtabs %}
