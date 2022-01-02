---
description: Join a new string value to all string elements in a Series.
---

# Series.str.join

> danfo.Series.str.**join**(valToJoin, joinChar, options)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L308)]

| Parameters | Type   | Description                                                     | Default                                                |
| ---------- | ------ | --------------------------------------------------------------- | ------------------------------------------------------ |
| valToJoin  | String | the string value you want to                                    |  ""                                                    |
| joinChar   | String | The delimiter to specify the joining                            | " "                                                    |
| options    | Object | **inplace**: Whether to perform the operation in-place or not.  | <p>{</p><p><strong>inplace</strong>: false</p><p>}</p> |

**Returns:**

&#x20;  ****   return **Series**

**Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower part', 'CAPITALS city', 'this is a sentence', 'SwAp CaSe']
let sf = new dfd.Series(data)
sf.str.join("new", "_").print()
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
╔═══╤════════════════════════╗
║ 0 │ lower part_new         ║
╟───┼────────────────────────╢
║ 1 │ CAPITALS city_new      ║
╟───┼────────────────────────╢
║ 2 │ this is a sentence_new ║
╟───┼────────────────────────╢
║ 3 │ SwAp CaSe_new          ║
╚═══╧════════════════════════╝
```
{% endtab %}
{% endtabs %}
