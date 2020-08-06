---
description: Converts all characters to uppercase.
---

# Series.str.toUpperCase

> danfo.Series.str.toUpperCase\(\)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L33)\]

**Parameters:** None

**Returns**:  Series \(String element\)

**Example**

Convert all characters in each string element to capital letter

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = ['lower boy', 'CAPITALS', 'sentence', 'SwApCaSe']
let sf = new dfd.Series(data)
sf.str.toUpperCase().print()
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
║ 0 │ LOWER BOY            ║
╟───┼──────────────────────╢
║ 1 │ CAPITALS             ║
╟───┼──────────────────────╢
║ 2 │ SENTENCE             ║
╟───┼──────────────────────╢
║ 3 │ SWAPCASE             ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

