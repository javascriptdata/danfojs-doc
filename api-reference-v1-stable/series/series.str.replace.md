---
description: Replace a word or character(s) in a String element
---

# Series.str.replace

> danfo.Series.str.replace(searchValue, replaceValue, options)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L191)]   &#x20;

| Parameters   | Type   | Description                                                     | Default                                                |
| ------------ | ------ | --------------------------------------------------------------- | ------------------------------------------------------ |
| searchValue  | string | String \| Character value to replace. Supports regex.           | ""                                                     |
| replaceValue | String | string to replace the searched string                           | ""                                                     |
| options      | Object | **inplace**: Whether to perform the operation in-place or not.  | <p>{</p><p><strong>inplace</strong>: false</p><p>}</p> |

**Returns:** Series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower', 'CAPITALS', 'this is a sentence', 'SwApCaSe']
let sf = new dfd.Series(data)
sf.str.replace("A", "XXX").print()
```
{% endtab %}

{% tab title="Browse" %}
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
║ 0 │ lower                ║
╟───┼──────────────────────╢
║ 1 │ CXXXPITALS           ║
╟───┼──────────────────────╢
║ 2 │ this is a sentence   ║
╟───┼──────────────────────╢
║ 3 │ SwXXXpCaSe           ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
