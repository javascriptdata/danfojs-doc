---
description: Return the sum of the values in a series.
---

# Series.sum

> danfo.Series.sum()&#x20;

**Parameter:** None

**Return:** Number

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [20, 30, 1, 2, 4, 57, 89, 0, 4]
let sf1 = new dfd.Series(data1)

console.log(sf1.sum())
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
207
```
{% endtab %}
{% endtabs %}

***
