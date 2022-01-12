---
description: Obtain the shape of a Series
---

# Series.shape

> danfo.Series.shape

**Parameters**: None

**Returns**: Array \[int, int]

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [30.21091, 40.190901, 3.564, 5.0212]
let sf1 = new dfd.Series(data1)

console.log(sf1.shape)
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
[ 4, 1 ]
```
{% endtab %}
{% endtabs %}
