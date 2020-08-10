---
description: Obtain the maximum value of columns per groups
---

# Groupby.max

> danfo.Groupby.max\(\)      \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/groupby.js#L309)\]

**Parameters:** None

**Returns**: DataFrame

**Example**

Obtain the maximum value for a column for each groups, group by one column

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")


let data =[{'A': ['foo', 'bar', 'foo', 'bar',
                         'foo', 'bar', 'foo', 'foo']},
            {'B': ['one', 'one', 'two', 'three',
                    'two', 'two', 'one', 'three']},
            {'C': [1,3,2,4,5,2,6,7]},
            {'D': [3,2,4,1,5,6,7,8]}
        ]

let df = new dfd.DataFrame(data)


let grp = df.groupby(["A"])
grp.col(["C"]).max().print()
```
{% endtab %}
{% endtabs %}

```text
 Shape: (2,2) 

╔═══╤═══════════════════╤═══════════════════╗
║   │ A                 │ C_max             ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ foo               │ 7                 ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ bar               │ 4                 ║
╚═══╧═══════════════════╧═══════════════════╝
```

Obtain the maximum value for two columns for each groups, group by one column

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")


let data =[{'A': ['foo', 'bar', 'foo', 'bar',
                         'foo', 'bar', 'foo', 'foo']},
            {'B': ['one', 'one', 'two', 'three',
                    'two', 'two', 'one', 'three']},
            {'C': [1,3,2,4,5,2,6,7]},
            {'D': [3,2,4,1,5,6,7,8]}
        ]

let df = new dfd.DataFrame(data)


let grp = df.groupby(["A"])
grp.col(["C","D"]).max().print()
```
{% endtab %}
{% endtabs %}

```text
 Shape: (2,3) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ C_max             │ D_max             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ 7                 │ 8                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ bar               │ 4                 │ 6                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Obtain the maximum value for a column for each groups, group by two column

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")


let data =[{'A': ['foo', 'bar', 'foo', 'bar',
                         'foo', 'bar', 'foo', 'foo']},
            {'B': ['one', 'one', 'two', 'three',
                    'two', 'two', 'one', 'three']},
            {'C': [1,3,2,4,5,2,6,7]},
            {'D': [3,2,4,1,5,6,7,8]}
        ]

let df = new dfd.DataFrame(data)


let grp = df.groupby(["A","B"])
grp.col(["C"]).max().print()
```
{% endtab %}
{% endtabs %}

```text
 Shape: (5,3) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C_max             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ two               │ 5                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ foo               │ three             │ 7                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ bar               │ one               │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ bar               │ two               │ 2                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Obtain the maximum value for two columns for each groups, group by two columns

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")


let data =[{'A': ['foo', 'bar', 'foo', 'bar',
                         'foo', 'bar', 'foo', 'foo']},
            {'B': ['one', 'one', 'two', 'three',
                    'two', 'two', 'one', 'three']},
            {'C': [1,3,2,4,5,2,6,7]},
            {'D': [3,2,4,1,5,6,7,8]}
        ]

let df = new dfd.DataFrame(data)


let grp = df.groupby(["A","B"])
grp.col(["C","D"]).max().print()
```
{% endtab %}
{% endtabs %}

```text
 Shape: (5,4) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C_max             │ D_max             ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 6                 │ 7                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ two               │ 5                 │ 5                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ foo               │ three             │ 7                 │ 8                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ bar               │ one               │ 3                 │ 2                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ bar               │ two               │ 2                 │ 6                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

