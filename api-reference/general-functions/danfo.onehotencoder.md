---
description: Encode categorical features as a one-hot numeric array.
---

# danfo.OneHotEncoder

class danfo.**OneHotEncoder**&#x20;

danfo.js provides the OneHotEncoder class for encoding values in Series and Arrays to one-hot numeric arrays. This is mostly used as a preprocessing step before most machine learning tasks.

The API is similar to scikit-learn's [OneHotEncoder](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.OneHotEncoder.html?highlight=onehotencoder#sklearn.preprocessing.OneHotEncoder), and provides a fit and transform method.

## **Examples**

### **Convert Series to Dummy codes**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    fruits: ['pear', 'mango', "pawpaw", "mango", "bean"],
    Count: [20, 30, 89, 12, 30],
    Country: ["NG", "NG", "GH", "RU", "RU"]
}


let df = new dfd.DataFrame(data)
let encode = new dfd.OneHotEncoder()

encode.fit(df['fruits'])
console.log(encode);

let sf_enc = encode.transform(df['fruits'].values)
console.log(sf_enc)

let new_sf = encode.transform(["mango", "bean"])
console.log(new_sf)
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
OneHotEncoder { '$labels': [ 'pear', 'mango', 'pawpaw', 'bean' ] }
[
  [ 1, 0, 0, 0 ],
  [ 0, 1, 0, 0 ],
  [ 0, 0, 1, 0 ],
  [ 0, 1, 0, 0 ],
  [ 0, 0, 0, 1 ]
]
[ [ 0, 1, 0, 0 ], [ 0, 0, 0, 1 ] ]
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
**Labels not found in the original data used for fitting are represented with 0s all through**
{% endhint %}

See also [LabelEncoder](danfo.labelencoder.md) and[ danfo.getDummies](danfo.get\_dummies.md)
