---
description: Returns the int position of the largest value in the series
---

# Series.argmax

> danfo.Series.argmax\(\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L975)\]

**Parameters**: None

**Returns**: int

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [1,30,20,40,50,70,90,200,10,20,12]
let sf = new dfd.Series(data)

sf.argmax()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
7
```
{% endtab %}
{% endtabs %}

