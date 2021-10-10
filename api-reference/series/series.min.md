---
description: Obtain the minimum value in a series
---

# Series.min

> danfo.Series.min()     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L303)]

**Parameter:** None

**Return:** Number

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [20, 30, 1, 2, 4, 57, 89, 0, 4]
let sf1 = new dfd.Series(data1)

console.log(sf1.min())
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
0
```
{% endtab %}
{% endtabs %}

****
