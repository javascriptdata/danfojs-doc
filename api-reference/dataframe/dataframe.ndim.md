---
description: >-
  Return an int representing the number of axes / array dimensions. Returns 1 if
  Series. Otherwise return 2 for DataFrame.
---

# DataFrame.ndim

danfo.DataFrame.**ndim** \[[source](https://github.com/opensource9ja/danfojs/blob/eb5919d2cac34271fc3b725fa24aa3ad4eacde37/danfojs/src/core/generic.js#L290)]

**Returns:**

&#x20;      ****       return **Int**

**Note:** To get the **shape** of the DataFrame use the .[shape](dataframe.shape.md) property.

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"A": [-20.1, 30, 47.3, -20],
            "B": [34, -4, 5, 6], 
            "C": [20, -20, 30, -40]}
let df = new dfd.DataFrame(data)

console.log(df.ndim)

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
2
```
{% endtab %}
{% endtabs %}
