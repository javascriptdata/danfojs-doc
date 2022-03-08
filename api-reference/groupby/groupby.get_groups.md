---
description: Obtain the data for each element of the groupby column
---

# Groupby.get\_groups

> danfo.Groupby.get\_groups(key) \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/groupby.js#L313)]

| Parameters | Type  | Description                   | default |
| ---------- | ----- | ----------------------------- | ------- |
| key        | Array | element of the groupby column |         |

**Returns**: DataFrame

**Example**

Group the dataframe by column A and obtain the group belonging to the values in column A

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

grp.get_groups(["foo"]).print()

grp.get_groups(["bar"]).print()
```
{% endtab %}
{% endtabs %}

```
//get groups for key "foo"
 Shape: (5,4) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 1                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ two               │ 2                 │ 4                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ foo               │ two               │ 5                 │ 5                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ foo               │ one               │ 6                 │ 7                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ foo               │ three             │ 7                 │ 8                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

//get groups for key "bar"

 Shape: (3,4) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ bar               │ one               │ 3                 │ 2                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ bar               │ three             │ 4                 │ 1                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ bar               │ two               │ 2                 │ 6                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Group dataframe by two columns and obtain their groups. Since the dataframe is grouped by two columns we most specify two keys in the get\_groups belonging to these two columns

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

grp.get_groups(["foo","one"]).print()

grp.get_groups(["bar","one"]).print()
```
{% endtab %}
{% endtabs %}

```
//get_groups(["foo","one"]


 Shape: (2,4) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 1                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ one               │ 6                 │ 7                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

//get_groups(["bar","one"])


 Shape: (1,4) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ bar               │ one               │ 3                 │ 2                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
