---
description: Obtain the data for each element of the groupby column
---

# Groupby.getGroup

> danfo.Groupby.getGroup(key\)      \[[source](https://github.com/javascriptdata/danfojs/blob/0d33e344b80a3ed54c91c9393ac3b583d4b0b1a4/src/danfojs-base/aggregators/groupby.ts#L523)\]

| Parameters | Type | Description | default |
| :--- | :--- | :--- | :--- |
| key | Array | element of the groupby column |  |

**Returns**: DataFrame

**Example**

Group the dataframe by column A and obtain the group belonging to the values in column A

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data ={A: ['foo', 'bar', 'foo', 'bar',
                'foo', 'bar', 'foo', 'foo'],
           B: ['one', 'one', 'two', 'three',
                'two', 'two', 'one', 'three'],
           C: [1,3,2,4,5,2,6,7],
           D: [3,2,4,1,5,6,7,8]
}

let df = new dfd.DataFrame(data)


let grp = df.groupby(["A"])

grp.getGroup(["foo"]).print()

grp.getGroup(["bar"]).print()
```
{% endtab %}
{% endtabs %}

```text
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

Group dataframe by two columns and obtain their groups. Since the dataframe is grouped by two columns we most specify two keys in the getGroups belonging to these two columns

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data ={A: ['foo', 'bar', 'foo', 'bar',
                'foo', 'bar', 'foo', 'foo'],
           B: ['one', 'one', 'two', 'three',
                'two', 'two', 'one', 'three'],
           C: [1,3,2,4,5,2,6,7],
           D: [3,2,4,1,5,6,7,8]
}

let df = new dfd.DataFrame(data)


let grp = df.groupby(["A","B"])

grp.getGroup(["foo","one"]).print()

grp.getGroup(["bar","one"]).print()
```
{% endtab %}
{% endtabs %}

```text
//getGroup(["foo","one"]


 Shape: (2,4) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 1                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ one               │ 6                 │ 7                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

//getGroup(["bar","one"])


 Shape: (1,4) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ bar               │ one               │ 3                 │ 2                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

