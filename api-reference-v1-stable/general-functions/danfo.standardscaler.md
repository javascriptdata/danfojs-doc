---
description: Standardize features by removing the mean and scaling to unit variance.
---

# danfo.StandardScaler

class danfo.**StandScaler** \[[source](https://github.com/opensource9ja/danfojs/blob/fe56860b0a303d218d60ba71dee6abf594401556/danfojs/src/core/frame.js#L254)]

danfo.js provides the StandardScaler class for the standardization of DataFrame and Series. The standard score of a sample `x` is calculated as:

> z = (x - u) / s

where `u` is the mean of the training samples or zero if `with_mean=False`, and `s` is the standard deviation of the training samples or one if `with_std=False`.

The API is similar to sklearn's [StandardScaler](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html?highlight=standardscaler#sklearn.preprocessing.StandardScaler), and provides a fit and transform method.&#x20;

## **Examples**

### Standardize Series Object

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let scaler = new dfd.StandardScaler()

let sf = new dfd.Series([100,1000,2000, 3000])
sf.print()

scaler.fit(sf)

let sf_enc = scaler.transform(sf)
sf_enc.print()
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
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 100                  ║
╟───┼──────────────────────╢
║ 1 │ 1000                 ║
╟───┼──────────────────────╢
║ 2 │ 2000                 ║
╟───┼──────────────────────╢
║ 3 │ 3000                 ║
╚═══╧══════════════════════╝

╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ -1.1375757455825806  ║
╟───┼──────────────────────╢
║ 1 │ -0.4191068708896637  ║
╟───┼──────────────────────╢
║ 2 │ 0.37919193506240845  ║
╟───┼──────────────────────╢
║ 3 │ 1.1774907112121582   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

### Standardize DataFrame Object

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
let scaler = new dfd.StandardScaler()

let data = [[100,1000,2000, 3000] ,
            [20, 30, 89, 12],
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
```
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
║ 0 │ -0.4185734987...  │ 0.48862975835...  │ 1.49663341045...  │ 2.50463700294...  ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ -0.4992137849...  │ -0.4891337454319  │ -0.4992137849...  │ -0.5092938542...  ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ -0.5183658599...  │ -0.5183658599...  │ -0.5183658599...  │ -0.5193738341...  ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

See also [MinMaxScaler](danfo.minmaxscaler.md)
