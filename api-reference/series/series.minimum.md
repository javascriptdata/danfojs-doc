---
description: Return the minimum between two series (element wise)
---

# Series.minimum

> danfo.Series.minimum(other)&#x20;

| Parameters | Type   | Description     | Default |
| ---------- | ------ | --------------- | ------- |
| other      | Series | series to match |         |

**Return:** {Series}

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [30, 40, 3, 5]
let data2 = [10, 41, 2, 0]
let sf1 = new dfd.Series(data1)
let sf2 = new dfd.Series(data2)
sf1.minimum(sf2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="output" %}
```
╔═══╤════╗
║ 0 │ 10 ║
╟───┼────╢
║ 1 │ 40 ║
╟───┼────╢
║ 2 │ 2  ║
╟───┼────╢
║ 3 │ 0  ║
╚═══╧════╝
```
{% endtab %}
{% endtabs %}
