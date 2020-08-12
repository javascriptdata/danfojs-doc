---
description: Obtain the standard deviation for a series
---

# Series.std

> danfo.Series.std\(\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L422)\]

**Parameter:** None

**Return:** Number

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [20, 30, 1, 2, 4, 57, 89, 0, 4]
let sf1 = new dfd.Series(data1)

console.log(sf1.std())
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
31.11671576500322
```
{% endtab %}
{% endtabs %}

 ****



