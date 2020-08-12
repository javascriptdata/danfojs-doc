---
description: Count the occurrence of values in columns per groups
---

# Groupby.count

> danfo.Groupby.count\(\)      \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/groupby.js#L249)\]

**Parameters**: None

**Return**: DataFrame

**Examples**

Obtain the variance of a column for each group, group by one column

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
grp.col(["C"]).count().print()
```
{% endtab %}
{% endtabs %}

```text

  Shape: (2,2) 

╔═══╤═══════════════════╤═══════════════════╗
║   │ A                 │ C_count           ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ foo               │ 5                 ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ bar               │ 3                 ║
╚═══╧═══════════════════╧═══════════════════╝
```

Obtain the var for two columns for each group, group by one column

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
grp.col(["C","D"]).count().print()
```
{% endtab %}
{% endtabs %}

```text
  Shape: (2,3) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ C_count           │ D_count           ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ 5                 │ 5                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ bar               │ 3                 │ 3                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Obtain the count for a column for each group, group by two columns

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
grp.col(["C"]).count().print()

```
{% endtab %}
{% endtabs %}

```text
  Shape: (5,3) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C_count           ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 2                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ two               │ 2                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ foo               │ three             │ 1                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ bar               │ one               │ 1                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ bar               │ two               │ 1                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Obtain the count for two columns for each group, group by two columns

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
grp.col(["C","D"]).count().print()
```
{% endtab %}
{% endtabs %}

```text
  
   Shape: (5,4) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C_count           │ D_count           ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 2                 │ 2                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ two               │ 2                 │ 2                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ foo               │ three             │ 1                 │ 1                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ bar               │ one               │ 1                 │ 1                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ bar               │ two               │ 1                 │ 1                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

\*\*\*\*

