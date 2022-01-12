---
description: Exported internal Tensoflow.js library
---

# danfo.tensorflow

danfo.**tensorflow**

**Returns:**

> &#x20;return [Tensorflow.js](https://www.npmjs.com/package/@tensorflow/tfjs) library

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
const tf = dfd.tensorflow

let tensor_arr = tf.tensor2d([[12, 34, 2.2, 2], [30, 30, 2.1, 7]])
console.log(tensor_arr)
```
{% endtab %}

{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <!--danfojs CDN -->
    <script src="https://cdn.jsdelivr.net/gh/opensource9ja/danfojs@latest/lib/bundle.js"></script>
    <title>Document</title>
</head>

<body>

    <script>
        const tf = dfd.tensorflow
        let tensor_arr = tf.tensor2d([[12, 34, 2.2, 2], [30, 30, 2.1, 7]])
        console.log(tensor_arr)
         
    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
Tensor {
  kept: false,
  isDisposedInternal: false,
  shape: [ 2, 4 ],
  dtype: 'float32',
  size: 8,
  strides: [ 4 ],
  dataId: {},
  id: 4,
  rankType: '2'
}
```
{% endtab %}
{% endtabs %}
