---
description: Obtain the number of groups
---

# Groupby.ngroups

> danfo.Groupby.ngroups    \[[source](https://github.com/javascriptdata/danfojs/blob/9bfda6dcb6b2b620591ec7b3340d35e3f801c8ab/src/danfojs-base/aggregators/groupby.ts#L598)\]

**Parameters**: None

**Return**: Number

**Examples**

Obtain the number of groups in a dataframe grouped by one column

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
console.log(grp.ngroups)
```
{% endtab %}
{% endtabs %}

```
2
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
console.log(grp.ngroups)
```
{% endtab %}
{% endtabs %}

```
6
```

****