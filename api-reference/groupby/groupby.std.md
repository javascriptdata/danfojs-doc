---
description: Obtain the standard deviation per groups for specified columns
---

# Groupby.std

> danfo.Groupby.**std**\(\)      \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/groupby.js#L262)\]

**Parameters**: None

**Return**: DataFrame

**Examples**

Obtain the standard deviation of a column for each groups, group by one column

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
grp.col(["C"]).std().print()
```
{% endtab %}
{% endtabs %}

```text

 Shape: (2,2) 

╔═══╤═══════════════════╤═══════════════════╗
║   │ A                 │ C_std             ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ foo               │ 2.58843582110...  ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ bar               │ 1                 ║
╚═══╧═══════════════════╧═══════════════════╝
```

Obtain the std for two columns for each groups, group by one column

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
grp.col(["C","D"]).std().print()
```
{% endtab %}
{% endtabs %}

```text
 Shape: (2,3) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ C_std             │ D_std             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ 2.58843582110...  │ 2.07364413533...  ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ bar               │ 1                 │ 2.64575131106...  ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Obtain the std for a column for each groups, group by two column

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
grp.col(["C"]).std().print()

```
{% endtab %}
{% endtabs %}

```text
    Shape: (5,3) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C_std             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 3.53553390593...  ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ two               │ 2.12132034355...  ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ foo               │ three             │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ bar               │ one               │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ bar               │ two               │ 0                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Obtain the std for two columns for each groups, group by two columns

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
grp.col(["C","D"]).std().print()
```
{% endtab %}
{% endtabs %}

```text
  
 Shape: (5,4) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C_std             │ D_std             ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 3.53553390593...  │ 2.82842712474...  ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ two               │ 2.12132034355...  │ 0.70710678118...  ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ foo               │ three             │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ bar               │ one               │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ bar               │ two               │ 0                 │ 0                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

\*\*\*\*

