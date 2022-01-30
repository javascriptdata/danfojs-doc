---
description: Obtain the last row of each groups
---

# Groupby.last

> danfo.Groupby.last    \[[source](https://github.com/javascriptdata/danfojs/blob/9bfda6dcb6b2b620591ec7b3340d35e3f801c8ab/src/danfojs-base/aggregators/groupby.ts#L635)\]

**Parameters**: None

**Return**: DataFrame

**Examples**

Obtain the size of each group for dataframe grouped by one column

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
grp.size().print()
```
{% endtab %}
{% endtabs %}

```
╔════════════╤═══════════════════╤═══════════════════╗
║            │ A_Group           │ applyOps          ║
╟────────────┼───────────────────┼───────────────────╢
║ 0          │ foo               │ 5                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ bar               │ 3                 ║
╚════════════╧═══════════════════╧═══════════════════╝
```

Obtain the size of each group in dataframe grouped by two columns

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
grp.size().print()
```
{% endtab %}
{% endtabs %}

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A_Group           │ B_Group           │ applyOps          ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ foo               │ one               │ 2                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ foo               │ two               │ 2                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ foo               │ three             │ 1                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ bar               │ one               │ 1                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4          │ bar               │ three             │ 1                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 5          │ bar               │ two               │ 1                 ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

****