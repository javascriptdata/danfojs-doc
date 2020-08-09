---
description: Obtain the size of a series
---

# Series.size

> danfo.Series.size  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/generic.js#L305)\]

**Parameters**: None

**Returns:** int

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [30.21091, 40.190901, 3.564, 5.0212]
let sf1 = new dfd.Series(data1)

console.log(sf1.size)
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
4
```
{% endtab %}
{% endtabs %}



