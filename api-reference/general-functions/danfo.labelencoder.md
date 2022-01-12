---
description: Encode target labels with value between 0 and n_classes-1.
---

# danfo.LabelEncoder

class danfo.**LabelEncoder**&#x20;

danfo.js provides the LabelEncoder class for encoding Series and Arrays to integer between 0 and n\_classes -1. This is mostly used as a preprocessing step before most machine learning tasks.

The API is similar to sklearn's [LabelEncoder](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.LabelEncoder.html?highlight=labelencoder#sklearn.preprocessing.LabelEncoder), and provides a fit and transform method.

## **Examples**

### **Label Encode values in a Series**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require('danfojs-node')

let data = ["dog","cat","man","dog","cat","man","man","cat"]
let series = new dfd.Series(data)

let encode = new dfd.LabelEncoder()

encode.fit(series)
console.log(encode);

let sf_enc = encode.transform(series.values)
console.log(sf_enc)

let new_sf = encode.transform(["dog","man"])
console.log(new_sf)
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
LabelEncoder { '$labels': { dog: 0, cat: 1, man: 2 } }
[
  0, 1, 2, 0,
  1, 2, 2, 1
]
[ 0, 2 ]
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
**Labels not found in the original data used for fitting are represented with -1**
{% endhint %}

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { fruits: ['pear', 'mango', "pawpaw", "mango", "bean"] ,
            Count: [20, 30, 89, 12, 30],
            Country: ["NG", "NG", "GH", "RU", "RU"]}


let df = new dfd.DataFrame(data)
let encode = new dfd.LabelEncoder()

encode.fit(df['fruits'])
console.log(encode);

let sf_enc = encode.transform(df['fruits'].values)
console.log(sf_enc);

let new_sf = encode.transform(["mango","mane"])
console.log(new_sf);
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
LabelEncoder { '$labels': { pear: 0, mango: 1, pawpaw: 2, bean: 3 } }
[ 0, 1, 2, 1, 3 ]
[ 1, -1 ]
```
{% endtab %}
{% endtabs %}

See also [OneHotEncoder](danfo.onehotencoder.md) and[ danfo.getDummies](danfo.get\_dummies.md)
