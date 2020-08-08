---
description: Obtain the number of unique values in a series
---

# Series.nunique

> danfo.Series.**nunique**\(\)       \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L750)\]

**Parameters**: None

**Returns:** int

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [1, 2, 3, 4, 5, 6, 7, 8, 1, 1, 22, 8, 5, 5, 5]
let sf = new dfd.Series(data1)

console.log(sf.nunique())
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Ouptut" %}
```text
9
```
{% endtab %}
{% endtabs %}

