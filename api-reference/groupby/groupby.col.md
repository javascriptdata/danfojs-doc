---
description: Obtain the column(s) per groups
---

# Groupby.col

> danfo.Groupby.col\(col\_names\)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/groupby.js#L104)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| col\_names | Array | List of column |  |

Returns: Groupby Data structure

Note:    This is similar to pandas `df.groupby(["column"])["colNames"]`

**Examples**

Obtain the column to perform group aggregate operation on

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

//select single column
let grpColumnC = grp.col(["C"])

// convert grouop internal data to dataFrame
grpColumnC.apply(x=> x).print()

//select multiple column
let grpColumnBD = grp.col(["B", "D"])

grpColumnBD.apply(x=> x).print()
```
{% endtab %}
{% endtabs %}

Apparently the output are not that useful unless you perform some operations like max\(\), count\(\) and the likes. 

```text
// select single column C

╔════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ C                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 0          │ foo               │ 1                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ foo               │ 2                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 2          │ foo               │ 5                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 3          │ foo               │ 6                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 4          │ foo               │ 7                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 5          │ bar               │ 3                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 6          │ bar               │ 4                 ║
╟────────────┼───────────────────┼───────────────────╢
║ 7          │ bar               │ 2                 ║
╚════════════╧═══════════════════╧═══════════════════╝

// select multiple column: B and D

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ D                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ foo               │ one               │ 3                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ foo               │ two               │ 4                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ foo               │ two               │ 5                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ foo               │ one               │ 7                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4          │ foo               │ three             │ 8                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 5          │ bar               │ one               │ 2                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 6          │ bar               │ three             │ 1                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 7          │ bar               │ two               │ 6                 ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝


```



