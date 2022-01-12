---
description: Return a the JavaScript array representation of the DataFrame.
---

# DataFrame.values

danfo.DataFrame.**values**&#x20;

**Note:** To get the [Tensorflow](https://js.tensorflow.org) tensor of the DataFrame, you can call the **.**[**tensor**](dataframe.tensor.md) property on the DataFrame.

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"A": [-20.1, 30, 47.3, -20],
            "B": [34, -4, 5, 6], 
            "C": [20, -20, 30, -40]}
            
let df = new dfd.DataFrame(data)

console.log(df.values)
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
[
  [ -20.1, 34, 20 ],
  [ 30, -4, -20 ],
  [ 47.3, 5, 30 ],
  [ -20, 6, -40 ]
]
```
{% endtab %}
{% endtabs %}
