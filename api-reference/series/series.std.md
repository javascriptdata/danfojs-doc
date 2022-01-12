---
description: Obtain the standard deviation for a series
---

# Series.std

> danfo.Series.std()&#x20;

**Parameter:** None

**Return:** Number

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [20, 30, 1, 2, 4, 57, 89, 0, 4]
let sf1 = new dfd.Series(data1)

console.log(sf1.std())
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
31.11671576500322
```
{% endtab %}
{% endtabs %}

\*\*\*\*
