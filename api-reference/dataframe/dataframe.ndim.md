---
description: >-
  Return an integer representing the number of dimensions. Returns 1 if Series.
  Otherwise return 2 for DataFrame.
---

# DataFrame.ndim

danfo.DataFrame.**ndim**&#x20;

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
