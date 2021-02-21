---
description: Transform features by scaling each feature to a range of max and min values.
---

# danfo.MinMaxScaler

class danfo.**MinMaxScaler** \[[source](https://github.com/opensource9ja/danfojs/blob/fe56860b0a303d218d60ba71dee6abf594401556/danfojs/src/core/frame.js#L254)\]

danfo.js provides the MinMaxScaler class for standardization of DataFrame and Series. This estimator scales and translates each feature individually such that it is in the given range on the training set, e.g. between zero and one.

This transformation is often used as an alternative to zero mean, unit variance scaling like [Standardscaler](danfo.standardscaler.md).

The API is similar to sklearn's [MinMaxScaler](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.MinMaxScaler.html?highlight=minmaxscaler#sklearn.preprocessing.MinMaxScaler), and provides a fit and transform method.

## **Examples**

### Standardize DataFrame Object using MinMaxScaler

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let scaler = new dfd.MinMaxScaler()

let data = [[100,1000,2000, 3000] ,
            [20, 30, 20, 10],
            [1, 1, 1, 0]]

let df = new dfd.DataFrame(data)
df.print()

scaler.fit(df)

let df_enc = scaler.transform(df)
df_enc.print()

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
║   │ 0                 │ 1                 │ 2                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 100               │ 1000              │ 2000              │ 3000              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 20                │ 30                │ 20                │ 10                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 1                 │ 1                 │ 1                 │ 0                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝


 Shape: (3,4)

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ 0                 │ 1                 │ 2                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 1                 │ 1                 │ 1                 │ 1                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 0.19191919267...  │ 0.02902902849...  │ 0.00950475223...  │ 0.00333333341...  ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 0                 │ 0                 │ 0                 │ 0                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Standardize Series Object Using MinMaxScaler

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
let scaler = new dfd.MinMaxScaler()

let data = [[100,1000,2000, 3000] ,
            [20, 30, 20, 10],
            [1, 1, 1, 0]]

let df = new dfd.DataFrame(data)
let sf = df.iloc({columns: ["0"]})

scaler.fit(sf)

let df_enc = scaler.transform(sf)
df_enc.print()

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

 Shape: (3,1)

╔═══╤═══════════════════╗
║   │ 0                 ║
╟───┼───────────────────╢
║ 0 │ 1                 ║
╟───┼───────────────────╢
║ 1 │ 0.19191919267...  ║
╟───┼───────────────────╢
║ 2 │ 0                 ║
╚═══╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

See also [MinMaxScaler](danfo.minmaxscaler.md)
