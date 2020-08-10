---
description: Obtain the mean of a series
---

# Series.mean

> danfo.Series.mean\(\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L253)\]

**Parameter:** None

**Return:** Number

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [20, 30, 1, 2, 4, 57, 89, 0, 4]
let sf1 = new dfd.Series(data1)

console.log(sf1.mean())
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
23.000001907348633
```
{% endtab %}
{% endtabs %}

\*\*\*\*

