---
description: The index (row labels) of the DataFrame.
---

# DataFrame.index

danfo.DataFrame.**index** \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L940)]

## **Examples**

Returns auto-generated** **index of a** **DataFrame

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"A": [-20.1, 30, 47.3, -20],
            "B": [34, -4, 5, 6], 
            "C": [20, -20, 30, -40]}
let df = new dfd.DataFrame(data)

console.log(df.index);
```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
[0, 1, 2, 3]
```
{% endtab %}
{% endtabs %}

Returns set** **index of a** **DataFrame

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"A": [-20.1, 30, 47.3, -20],
            "B": [34, -4, 5, 6], 
            "C": [20, -20, 30, -40]}
let df = new dfd.DataFrame(data, {index: ["r1", "r2", "r3", "r4"])

console.log(df.index);
```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
[ 'r1', 'r2', 'r3', 'r4' ]
```
{% endtab %}
{% endtabs %}
