---
description: Obtain the tensor representation of the values in a Series
---

# Series.tensor

> danfo.Series.tensor&#x20;

**Parameters**: None

**Returns**: Tensorflow tensor

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [30.21091, 40.190901, 3.564, 5.0212]
let sf1 = new dfd.Series(data1)

console.log(sf1.tensor)
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
Tensor {
  kept: false,
  isDisposedInternal: false,
  shape: [ 4 ],
  dtype: 'float32',
  size: 4,
  strides: [],
  dataId: {},
  id: 2,
  rankType: '1',
  scopeId: 0
}
```
{% endtab %}
{% endtabs %}
