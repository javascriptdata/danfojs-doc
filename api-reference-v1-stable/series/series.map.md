---
description: Map the value of a series to a function or Object
---

# Series.map

> danfo.series.**map**(callable) \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L685)]

| Parameter | Type               | Description                                                                                    | Default                               |
| --------- | ------------------ | ---------------------------------------------------------------------------------------------- | ------------------------------------- |
| callable  | Function or Object | A function or object({})                                                                       |                                       |
| options   | Object             | inplace: Boolean indicating whether to perform the operation inplace or not. Defaults to false | <p>{</p><p>inplace: false</p><p>}</p> |

**Example**

Mapping the element in a Series  words in an Object

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let sf = new dfd.Series([1, 2, 3, 4])
let map = { 1: "ok", 2: "okie", 3: "frit", 4: "gop" }
sf.map(map).print()

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
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ ok                   ║
╟───┼──────────────────────╢
║ 1 │ okie                 ║
╟───┼──────────────────────╢
║ 2 │ frit                 ║
╟───┼──────────────────────╢
║ 3 │ gop                  ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

Mapping values in a Series to a representation using functions.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let sf = new dfd.Series([1,2,3,4])

sf.map((x)=>{
    return `I have ${x} cat(s)`
}).print()

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
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ I have 1 cat(s)      ║
╟───┼──────────────────────╢
║ 1 │ I have 2 cat(s)      ║
╟───┼──────────────────────╢
║ 2 │ I have 3 cat(s)      ║
╟───┼──────────────────────╢
║ 3 │ I have 4 cat(s)      ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
