---
description: Detect Missing values
---

# Series.isNa

> danfo.Series.isNa()&#x20;

**Parameters**: None

**Returns**: Series (Boolean element)

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [NaN, undefined, "girl", "Man"]
let sf = new dfd.Series(data1)

sf.isNa().print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤═══════╗
║ 0 │ true  ║
╟───┼───────╢
║ 1 │ true  ║
╟───┼───────╢
║ 2 │ false ║
╟───┼───────╢
║ 3 │ false ║
╚═══╧═══════╝
```
{% endtab %}
{% endtabs %}
