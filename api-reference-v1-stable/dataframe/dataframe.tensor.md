---
description: >-
  Return a Tensorflow tensor representation of the DataFrame. Only the values in
  the DataFrame will be returned, the axes labels will be removed.
---

# DataFrame.tensor

danfo.DataFrame.**tensor** \[[source](https://github.com/opensource9ja/danfojs/blob/eb5919d2cac34271fc3b725fa24aa3ad4eacde37/danfojs/src/core/generic.js#L290)]

**Returns:**

&#x20;      ****       return **tf.tensor**

> **Note:** [Tensorflow](https://js.tensorflow.org/api/latest/#tensor) tensors have single dtype, and will replace any string value with  NaN. Use with care.&#x20;

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20, 30, 47.3, -20] ,
             "B": [34, -4, 5, 6] ,
             "C": [20, 20, 30, 30]}
             
let df = new dfd.DataFrame(data)
let tf_tensor = df.tensor

console.log(tf_tensor.dtype);

console.log(tf_tensor);

tf_tensor.print()
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
float32
Tensor
    [[-20       , 34, 20],
     [30        , -4, 20],
     [47.2999992, 5 , 30],
     [-20       , 6 , 30]]
```
{% endtab %}
{% endtabs %}

String values in a Tensor are represented as NaN, so ensure to transform them before working with tensor representations.&#x20;

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Abs": [20.2, 30, 47.3] ,
             "Count": [34, 5, 6] ,
             "country code": ["NG", "FR", "GH"] }


let df = new dfd.DataFrame(data)
let tf_tensor = df.tensor

console.log(tf_tensor.dtype);

console.log(tf_tensor);

tf_tensor.print()
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
float32 

Tensor {
  kept: false,
  isDisposedInternal: false,
  shape: [ 3, 3 ],
  dtype: 'float32',
  size: 9,
  strides: [ 3 ],
  dataId: {},
  id: 0,
  rankType: '2'
}

Tensor
    [[20.2000008, 34, NaN],
     [30        , 4 , NaN],
     [47.2999992, 5 , NaN]]
```
{% endtab %}
{% endtabs %}
