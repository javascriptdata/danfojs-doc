---
description: Returns the int position of the smallest value in the series
---

# Series.argMin

> danfo.Series.argMin() \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L987)]

**Parameters**: None

**Returns**: int

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [1,30,20,40,50,70,90,200,10,20,12]
let sf = new dfd.Series(data)

sf.argMin()
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
