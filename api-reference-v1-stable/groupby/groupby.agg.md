---
description: Obtain data aggregate per groups for each column
---

# Groupby.agg

> danfo.Groupby.**agg**(kwargs)       \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/groupby.js#L349)]

| Parameters | Type   | Description                                                                                               | Default |
| ---------- | ------ | --------------------------------------------------------------------------------------------------------- | ------- |
| kwargs     | Object | kwargs contain keys which are column names in the dataframe, and the values are operation to be performed |         |

**Return: **DataFrame

**Examples**

Using mean and sum aggregate

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
grp.agg({"C":"mean","D":"sum"}).print()
```
{% endtab %}
{% endtabs %}

```
 Shape: (2,3) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ C_mean            │ D_sum             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ 4.19999980926...  │ 27                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ bar               │ 3                 │ 9                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Mean and Sum aggregate on dataframe groupby two column

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
grp.agg({"C":"mean","D":"sum"}).print()
```
{% endtab %}
{% endtabs %}

```
 Shape: (5,4) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C_mean            │ D_sum             ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 3.5               │ 10                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ two               │ 3.5               │ 9                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ foo               │ three             │ 7                 │ 8                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ bar               │ one               │ 3                 │ 2                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ bar               │ two               │ 2                 │ 6                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
