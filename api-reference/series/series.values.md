---
description: Obtain the values in a series
---

# Series.values

> danfo.Series.values&#x20;

**Parameters:** None

**Returns**: Array

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [30.21091, 40.190901, 3.564, 5.0212]
let sf1 = new dfd.Series(data1)

console.log(sf1.values)
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
[ 30.21091, 40.190901, 3.564, 5.0212 ]
```
{% endtab %}
{% endtabs %}
