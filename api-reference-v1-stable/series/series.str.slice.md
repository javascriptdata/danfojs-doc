---
description: Obtain the substring of each element in a series
---

# Series.str.slice

> danfo.Series.str.slice(startIndex, endIndex, options)  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L235)]

| Parameters | Type   | Description                                                     | Default                                                |
| ---------- | ------ | --------------------------------------------------------------- | ------------------------------------------------------ |
| startIndex | Number | specify the index to start obtaining the substring              | 0                                                      |
| endIndex   | Number | specify the index to end the substring                          | 1                                                      |
| options    | Object | **inplace**: Whether to perform the operation in-place or not.  | <p>{</p><p><strong>inplace</strong>: false</p><p>}</p> |

**Returns:**

&#x20; ****  return Series.

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower part ', ' CAPITALS city', ' this is a sentence', '  SwAp CaSe']
let sf = new dfd.Series(data)
sf.str.slice(2, 4).print()
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
║ 0 │ we                   ║
╟───┼──────────────────────╢
║ 1 │ AP                   ║
╟───┼──────────────────────╢
║ 2 │ hi                   ║
╟───┼──────────────────────╢
║ 3 │ Sw                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
