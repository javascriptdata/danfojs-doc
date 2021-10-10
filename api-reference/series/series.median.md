---
description: Obtain the median of a series
---

# Series.median

> danfo.Series.median()     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L274)]

**Parameter:** None

**Return:** Number

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [20, 30, 1, 2, 4, 57, 89, 0, 4]
let sf1 = new dfd.Series(data1)

console.log(sf1.median())
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
4
```
{% endtab %}
{% endtabs %}

****
