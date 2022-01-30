---
description: Obtain the variance per groups for a specified column
---

# Groupby.var

> danfo.Groupby.**var**()     \[[source](https://github.com/javascriptdata/danfojs/blob/9bfda6dcb6b2b620591ec7b3340d35e3f801c8ab/src/danfojs-base/aggregators/groupby.ts#L456)]

**Parameters**: None

**Return**: DataFrame

**Examples**

Obtain the variance of a column for each group, group by one column

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
grp.col(["C"]).var().print()
```
{% endtab %}
{% endtabs %}

```

 Shape: (2,2) 

╔═══╤═══════════════════╤═══════════════════╗
║   │ A                 │ C_var             ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ foo               │ 6.7               ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ bar               │ 1                 ║
╚═══╧═══════════════════╧═══════════════════╝
```

Obtain the var for two columns for each group, group by one column

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
grp.col(["C","D"]).var().print()
```
{% endtab %}
{% endtabs %}

```
 Shape: (2,3) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ C_var             │ D_var             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ 6.7               │ 4.3               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ bar               │ 1                 │ 7                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Obtain the var for a column for each group, group by two columns

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
grp.col(["C"]).var().print()

```
{% endtab %}
{% endtabs %}

```
 Shape: (5,3) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C_var             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 12.5              ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ two               │ 4.5               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ foo               │ three             │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ bar               │ one               │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ bar               │ two               │ 0                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Obtain the var for two columns for each group, group by two columns

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
grp.col(["C","D"]).var().print()
```
{% endtab %}
{% endtabs %}

```
  
  Shape: (5,4) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C_var             │ D_var             ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 12.5              │ 8                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ two               │ 4.5               │ 0.5               ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ foo               │ three             │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ bar               │ one               │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ bar               │ two               │ 0                 │ 0                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

****
