---
description: Standardize features by removing the mean and scaling to unit variance.
---

# danfo.StandardScaler

class danfo.**StandScaler**&#x20;

danfo.js provides the StandardScaler class for the standardization of DataFrame and Series. The standard score of a sample `x` is calculated as:

> z = (x - u) / s

where `u` is the mean of the training samples or zero if `with_mean=False`, and `s` is the standard deviation of the training samples or one if `with_std=False`.

The API is similar to sklearn's [StandardScaler](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html?highlight=standardscaler#sklearn.preprocessing.StandardScaler), and provides a fit and transform method.

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
╔═══╤══════╗
║ 0 │ 100  ║
╟───┼──────╢
║ 1 │ 1000 ║
╟───┼──────╢
║ 2 │ 2000 ║
╟───┼──────╢
║ 3 │ 3000 ║
╚═══╧══════╝

╔═══╤═════════════════════╗
║ 0 │ -1.3135592937469482 ║
╟───┼─────────────────────╢
║ 1 │ -0.4839428961277008 ║
╟───┼─────────────────────╢
║ 2 │ 0.4378530979156494  ║
╟───┼─────────────────────╢
║ 3 │ 1.3596490621566772  ║
╚═══╧═════════════════════╝
```
{% endtab %}
{% endtabs %}

### Standardize DataFrame Object

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


let data = [[100, 1000, 2000, 3000],
        [20, 30, 89, 12],
        [1, 1, 1, 0]]

let df = new dfd.DataFrame(data, { columns: ['a', 'b', 'c', 'd'] })
df.print()

let scaler = new dfd.StandardScaler()
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
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ a                 │ b                 │ c                 │ d                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ 100               │ 1000              │ 2000              │ 3000              ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ 20                │ 30                │ 89                │ 12                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ 1                 │ 1                 │ 1                 │ 0                 ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ a                 │ b                 │ c                 │ d                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ 1.3909024000167…  │ 1.4137537479400…  │ 1.4131401777267…  │ 1.4142049551010…  ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ -0.473994612693…  │ -0.675643563270…  │ -0.658863127231…  │ -0.702851355075…  ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ -0.916907668113…  │ -0.738110065460…  │ -0.754277229309…  │ -0.711353600025…  ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

See also [MinMaxScaler](danfo.minmaxscaler.md)
