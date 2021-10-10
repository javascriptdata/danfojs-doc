---
description: Returns an Array representing the dimensionality of the DataFrame.
---

# DataFrame.shape

danfo.DataFrame.**shape** \[[source](https://github.com/opensource9ja/danfojs/blob/eb5919d2cac34271fc3b725fa24aa3ad4eacde37/danfojs/src/core/generic.js#L290)]

**Returns:**

**       **return** Int**

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"A": [-20.1, 30, 47.3, -20],
            "B": [34, -4, 5, 6], 
            "C": [20, -20, 30, -40]}
let df = new dfd.DataFrame(data, {index: ["a", "b", "c", "d"]})

console.log(df.shape)


```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
[4,3]
```
{% endtab %}
{% endtabs %}
