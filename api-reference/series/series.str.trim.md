---
description: Remove leading and trailing Whitespace from a String element
---

# Series.str.trim

> danfo.Series.str.**trim**\(\)  **\[**[**source**](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L293)**\]**

**Parameters:** None

**Returns:**

         ****return Series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

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
```text
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

