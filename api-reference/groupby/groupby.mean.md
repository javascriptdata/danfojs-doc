---
description: Obtain the mean per groups for each column(s)
---

# Groupby.mean

> danfo.Series.mean\(\)      \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/groupby.js#L274)\]

**Parameters**: None

**Return**: DataFrame

**Examples**

Obtain the mean of a column for each groups, group by one column

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data ={'A': ['foo', 'bar', 'foo', 'bar',
                'foo', 'bar', 'foo', 'foo'],
           'B': ['one', 'one', 'two', 'three',
                'two', 'two', 'one', 'three'],
           'C': [1,3,2,4,5,2,6,7],
           'D': [3,2,4,1,5,6,7,8]
        }

let df = new dfd.DataFrame(data)


let grp = df.groupby(["A"])
grp.col(["C"]).mean().print()
```
{% endtab %}
{% endtabs %}

```text

  Shape: (2,2) 

╔═══╤═══════════════════╤═══════════════════╗
║   │ A                 │ C_mean            ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ foo               │ 4.19999980926...  ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ bar               │ 3                 ║
╚═══╧═══════════════════╧═══════════════════╝
```

Obtain the mean for two columns for each groups, group by one column

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")


let data ={'A': ['foo', 'bar', 'foo', 'bar',
                'foo', 'bar', 'foo', 'foo'],
           'B': ['one', 'one', 'two', 'three',
                'two', 'two', 'one', 'three'],
           'C': [1,3,2,4,5,2,6,7],
           'D': [3,2,4,1,5,6,7,8]
        }

let df = new dfd.DataFrame(data)


let grp = df.groupby(["A"])
grp.col(["C","D"]).mean().print()
```
{% endtab %}
{% endtabs %}

```text
 Shape: (2,3) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ C_mean            │ D_mean            ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ 4.19999980926...  │ 5.40000009536...  ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ bar               │ 3                 │ 3                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Obtain the mean for a column for each groups, group by two column

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data ={'A': ['foo', 'bar', 'foo', 'bar',
                'foo', 'bar', 'foo', 'foo'],
           'B': ['one', 'one', 'two', 'three',
                'two', 'two', 'one', 'three'],
           'C': [1,3,2,4,5,2,6,7],
           'D': [3,2,4,1,5,6,7,8]
        }

let df = new dfd.DataFrame(data)


let grp = df.groupby(["A","B"])
grp.col(["C"]).mean().print()
```
{% endtab %}
{% endtabs %}

```text
    Shape: (5,3) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C_mean            ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 3.5               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ two               │ 3.5               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ foo               │ three             │ 7                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ bar               │ one               │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ bar               │ two               │ 2                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Obtain the mean for two columns for each groups, group by two columns

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data ={'A': ['foo', 'bar', 'foo', 'bar',
                'foo', 'bar', 'foo', 'foo'],
           'B': ['one', 'one', 'two', 'three',
                'two', 'two', 'one', 'three'],
           'C': [1,3,2,4,5,2,6,7],
           'D': [3,2,4,1,5,6,7,8]
        }

let df = new dfd.DataFrame(data)


let grp = df.groupby(["A","B"])
grp.col(["C","D"]).mean().print()
```
{% endtab %}
{% endtabs %}

```text
    Shape: (5,4) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C_mean            │ D_mean            ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 3.5               │ 5                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ two               │ 3.5               │ 4.5               ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ foo               │ three             │ 7                 │ 8                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ bar               │ one               │ 3                 │ 2                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ bar               │ two               │ 2                 │ 6                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

\*\*\*\*

