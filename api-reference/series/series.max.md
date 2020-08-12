---
description: Obtain the maximum value in a Series
---

# Series.max

> danfo.Series.max\(\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L317)\]

**Parameter:** None

**Return:** Number

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [20, 30, 1, 2, 4, 57, 89, 0, 4]
let sf1 = new dfd.Series(data1)

console.log(sf1.max())
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
89
```
{% endtab %}
{% endtabs %}

\*\*\*\*

