---
description: Obtain data aggregate per groups for each column
---

# Groupby.agg

> danfo.Groupby.**agg**(kwargs)       \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/groupby.js#L349)]

| Parameters | Type   | Description                                                                                               | Default |
| ---------- | ------ | --------------------------------------------------------------------------------------------------------- | ------- |
| ops    | Object | keys are column names and `values` are aggregation operator |   {}      |

**Return:** DataFrame

**Examples**

**Aggregation using one aggregate operator per column**

1) Assigning `mean` and `sum` aggregate to different column 

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


let data ={'A': ['foo', 'bar', 'foo', 'bar',
                'foo', 'bar', 'foo', 'foo'],
           'B': ['one', 'one', 'two', 'three',
                'two', 'two', 'one', 'three'],
           'C': [1,3,2,4,5,2,6,7],
           'D': [3,2,4,1,5,6,7,8]
        }

let df = new dfd.DataFrame(data)

let grp = df.groupby(["A"])
grp.agg({C:"mean",D:"sum"}).print()
```
{% endtab %}
{% endtabs %}

```
 Shape: (2,3) 

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ C_mean            │ D_sum             ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ foo               │ 4.2               │ 27                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ bar               │ 3                 │ 9                 ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

2) Mean and Sum aggregate on dataframe grouped by two column

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


let data ={'A': ['foo', 'bar', 'foo', 'bar',
                'foo', 'bar', 'foo', 'foo'],
           'B': ['one', 'one', 'two', 'three',
                'two', 'two', 'one', 'three'],
           'C': [1,3,2,4,5,2,6,7],
           'D': [3,2,4,1,5,6,7,8]
        }

let df = new dfd.DataFrame(data)

let grp = df.groupby(["A","B"])
grp.agg({C:"mean",D:"sum"}).print()
```
{% endtab %}
{% endtabs %}

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C_mean            │ D_sum             ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ foo               │ one               │ 3.5               │ 10                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ foo               │ two               │ 3.5               │ 9                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ foo               │ three             │ 7                 │ 8                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ bar               │ one               │ 3                 │ 2                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4          │ bar               │ three             │ 4                 │ 1                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 5          │ bar               │ two               │ 2                 │ 6                 ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

**Aggregation using two or more  aggregate operator per column**

Assigning `mean` and `sum`, `min`, `std`, `count` aggregate to different column 

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


let data ={'A': ['foo', 'bar', 'foo', 'bar',
                'foo', 'bar', 'foo', 'foo'],
           'B': ['one', 'one', 'two', 'three',
                'two', 'two', 'one', 'three'],
           'C': [1,3,2,4,5,2,6,7],
           'D': [3,2,4,1,5,6,7,8]
        }

let df = new dfd.DataFrame(data)

let grp = df.groupby(["A"])
grp.agg({C:["mean", "sum", "min"],
         D:["sum", "count", "std"]}).print()
```
{% endtab %}
{% endtabs %}

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ C_mean            │ C_sum             │ C_min             │ D_sum             │ D_count           │ D_std             ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ foo               │ 4.2               │ 21                │ 1                 │ 27                │ 5                 │ 2.0736441353327…  ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ bar               │ 3                 │ 9                 │ 2                 │ 9                 │ 3                 │ 2.6457513110645…  ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```