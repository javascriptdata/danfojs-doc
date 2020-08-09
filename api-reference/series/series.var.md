---
description: Calculate the variance  of a Series
---

# Series.var

> danfo.Series.var\(\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L436)\]

**Parameter:** None

**Return:** Number

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [20, 30, 1, 2, 4, 57, 89, 0, 4]
let sf1 = new dfd.Series(data1)

console.log(sf1.var())
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
968.25
```
{% endtab %}
{% endtabs %}

