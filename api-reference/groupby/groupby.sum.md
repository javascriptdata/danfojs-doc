---
description: Obtain the sum per groups for columns
---

# Groupby.sum

> danfo.Groupby.sum\(\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/groupby.js#L262)\]

**Parameters**: None

**Return**: DataFrame

**Examples**

Obtain the sum of a column for each groups, group by one column

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
grp.col(["C"]).sum().print()
```
{% endtab %}
{% endtabs %}

```text

 Shape: (2,2) 

╔═══╤═══════════════════╤═══════════════════╗
║   │ A                 │ C_sum             ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ foo               │ 21                ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ bar               │ 9                 ║
╚═══╧═══════════════════╧═══════════════════╝
```

Obtain the sum for two columns for each groups, group by one column

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
grp.col(["C","D"]).sum().print()
```
{% endtab %}
{% endtabs %}

```text
 Shape: (2,3) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ C_sum             │ D_sum             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ 21                │ 27                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ bar               │ 9                 │ 9                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Obtain the sum for a column for each groups, group by two column

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
grp.col(["C"]).sum().print()
```
{% endtab %}
{% endtabs %}

```text
   Shape: (5,3) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C_sum             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 7                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ two               │ 7                 ║
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
grp.col(["C","D"]).sum().print()
```
{% endtab %}
{% endtabs %}

```text
   Shape: (5,4) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C_sum             │ D_sum             ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 7                 │ 10                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ two               │ 7                 │ 9                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ foo               │ three             │ 7                 │ 8                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ bar               │ one               │ 3                 │ 2                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ bar               │ two               │ 2                 │ 6                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

\*\*\*\*

