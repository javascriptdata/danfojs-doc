---
description: Remove leading and trailing Whitespace from a String element
---

# Series.str.trim

> danfo.Series.str.**trim**(options)  **\[**[**source**](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L293)**]**

| Parameters | Type   | Description                                                     | Default                                                |
| ---------- | ------ | --------------------------------------------------------------- | ------------------------------------------------------ |
| options    | Object | **inplace**: Whether to perform the operation in-place or not.  | <p>{</p><p><strong>inplace</strong>: false</p><p>}</p> |

**Returns:**

&#x20;        ****         return Series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower part ', ' CAPITALS city', ' this is a sentence', '  SwAp CaSe']
let sf = new dfd.Series(data)
sf.str.trim().print()
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
║ 0 │ lower part           ║
╟───┼──────────────────────╢
║ 1 │ CAPITALS city        ║
╟───┼──────────────────────╢
║ 2 │ this is a sentence   ║
╟───┼──────────────────────╢
║ 3 │ SwAp CaSe            ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
