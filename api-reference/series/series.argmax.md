---
description: Returns the int position of the largest value in the series
---

# Series.argMax

> danfo.Series.argMax()&#x20;

**Parameters**: None

**Returns**: int

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [1,30,20,40,50,70,90,200,10,20,12]
let sf = new dfd.Series(data)

sf.argMax()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
7
```
{% endtab %}
{% endtabs %}
