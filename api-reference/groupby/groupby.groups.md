---
description: Obtain groupby internal data object
---

# Groupby.ngroups

> danfo.Groupby.groups   \[[source](https://github.com/javascriptdata/danfojs/blob/9bfda6dcb6b2b620591ec7b3340d35e3f801c8ab/src/danfojs-base/aggregators/groupby.ts#L598)\]

**Parameters**: None

**Return**: Object

**Examples**

Obtain the group object for grouped by single column dataframe

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
console.log(grp.groups)
```
{% endtab %}
{% endtabs %}

```
{
  foo: {
    A: [ 'foo', 'foo', 'foo', 'foo', 'foo' ],
    B: [ 'one', 'two', 'two', 'one', 'three' ],
    C: [ 1, 2, 5, 6, 7 ],
    D: [ 3, 4, 5, 7, 8 ]
  },
  bar: {
    A: [ 'bar', 'bar', 'bar' ],
    B: [ 'one', 'three', 'two' ],
    C: [ 3, 4, 2 ],
    D: [ 2, 1, 6 ]
  }
}
```

Obtain the group object for grouped by two column dataframe

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
console.log(grp.groups)
```
{% endtab %}
{% endtabs %}

```
{
  'foo-one': {
    A: [ 'foo', 'foo' ],
    B: [ 'one', 'one' ],
    C: [ 1, 6 ],
    D: [ 3, 7 ]
  },
  'bar-one': { A: [ 'bar' ], B: [ 'one' ], C: [ 3 ], D: [ 2 ] },
  'foo-two': {
    A: [ 'foo', 'foo' ],
    B: [ 'two', 'two' ],
    C: [ 2, 5 ],
    D: [ 4, 5 ]
  },
  'bar-three': { A: [ 'bar' ], B: [ 'three' ], C: [ 4 ], D: [ 1 ] },
  'bar-two': { A: [ 'bar' ], B: [ 'two' ], C: [ 2 ], D: [ 6 ] },
  'foo-three': { A: [ 'foo' ], B: [ 'three' ], C: [ 7 ], D: [ 8 ] }
}
```

****