---
description: Encode categorical features as a one-hot numeric array.
---

# danfo.OneHotEncoder

class danfo.**OneHotEncoder** \[[source](https://github.com/opensource9ja/danfojs/blob/fe56860b0a303d218d60ba71dee6abf594401556/danfojs/src/core/frame.js#L254)\]

danfo.js provides the OneHotEncoder class for encoding values in Series and Arrays to one-hot numeric arrays. This is mostly used as a preprocessing step before most machine learning tasks. 

The API is similar to sklearn's [OneHotEncoder](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.OneHotEncoder.html?highlight=onehotencoder#sklearn.preprocessing.OneHotEncoder), and provides a fit and transform method. 

## **Examples**

### **Convert Series to Dummy codes**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { fruits: ['pear', 'mango', "pawpaw", "mango", "bean"],
            Count: [20, 30, 89, 12, 30],
            Country: ["NG", "NG", "GH", "RU", "RU"]}


let df = new dfd.DataFrame(data)
let encode = new dfd.OneHotEncoder()

encode.fit(df['fruits'])
console.log(encode);

let sf_enc = encode.transform(df['fruits'].values)
sf_enc.print()

let new_sf = encode.transform(["mango","bean"])
new_sf.print()
```
{% endtab %}

{% tab title="Browser" %}
```

```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ pear              │ mango             │ pawpaw            │ bean              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 1                 │ 0                 │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 0                 │ 1                 │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 0                 │ 0                 │ 1                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 0                 │ 1                 │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ 0                 │ 0                 │ 0                 │ 1                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝


 Shape: (2,4) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ pear              │ mango             │ pawpaw            │ bean              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 0                 │ 1                 │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 0                 │ 0                 │ 0                 │ 1                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
**Labels not found in the original data used for fitting are represented with 0s all through**
{% endhint %}

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { fruits: ['pear', 'mango', "pawpaw", "mango", "bean"] ,
            Count: [20, 30, 89, 12, 30],
            Country: ["NG", "NG", "GH", "RU", "RU"]}


let df = new dfd.DataFrame(data)
let encode = new dfd.OneHotEncoder()

encode.fit(df['fruits'])
console.log(encode);

let sf_enc = encode.transform(df['fruits'].values)
sf_enc.print()

let new_sf = encode.transform(["mango","woman", "cup"])
new_sf.print()
```
{% endtab %}

{% tab title="Browser" %}
```

```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ pear              │ mango             │ pawpaw            │ bean              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 1                 │ 0                 │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 0                 │ 1                 │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 0                 │ 0                 │ 1                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 0                 │ 1                 │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ 0                 │ 0                 │ 0                 │ 1                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝


 Shape: (3,4) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ pear              │ mango             │ pawpaw            │ bean              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 0                 │ 1                 │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 0                 │ 0                 │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 0                 │ 0                 │ 0                 │ 0                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

```
{% endtab %}
{% endtabs %}

See also [LabelEncoder](danfo.labelencoder.md) and[ danfo.get\_dummies](danfo.get_dummies.md)

