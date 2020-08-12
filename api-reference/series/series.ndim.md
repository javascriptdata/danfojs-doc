---
description: Obtain the dimension of a series
---

# Series.ndim

> danfo.Series.ndim  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/generic.js#L209)\]

**Parameters:** None

**Returns:** int

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [30.21091, 40.190901, 3.564, 5.0212]
let sf1 = new dfd.Series(data1)

console.log(sf1.ndim)
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
1
```
{% endtab %}
{% endtabs %}

