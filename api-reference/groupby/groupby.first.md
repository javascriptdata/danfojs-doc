---
description: Obtain the first row of each groups
---

# Groupby.first

> danfo.Groupby.first    \[[source](https://github.com/javascriptdata/danfojs/blob/9bfda6dcb6b2b620591ec7b3340d35e3f801c8ab/src/danfojs-base/aggregators/groupby.ts#L615)\]

**Parameters**: None

**Return**: DataFrame

**Examples**

Obtain the first row of each group for dataframe grouped by one column

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
grp.first().print()
```
{% endtab %}
{% endtabs %}

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A_Group           │ A                 │ B                 │ C                 │ D                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ foo               │ foo               │ one               │ 1                 │ 3                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ bar               │ bar               │ one               │ 3                 │ 2                 ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Obtain the number of groups in dataframe grouped by two columns

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
grp.first().print()
```
{% endtab %}
{% endtabs %}

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A_Group           │ B_Group           │ A                 │ B                 │ C                 │ D                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ foo               │ one               │ foo               │ one               │ 1                 │ 3                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ foo               │ two               │ foo               │ two               │ 2                 │ 4                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ foo               │ three             │ foo               │ three             │ 7                 │ 8                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ bar               │ one               │ bar               │ one               │ 3                 │ 2                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4          │ bar               │ three             │ bar               │ three             │ 4                 │ 1                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 5          │ bar               │ two               │ bar               │ two               │ 2                 │ 6                 ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

****