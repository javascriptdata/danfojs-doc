---
description: Converts all characters to lower case.
---

# Series.str.toLowerCase

> danfo.Series.str.toLowerCase\(\)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L20)\]

**Parameters:** None

**Returns**:  Series \(String element\)

**Example**

Convert all characters in each string element to small letter

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = ['LOWER BOY', 'CAPITALS', 'SENTENCE', 'SWAPCASE']
let sf = new dfd.Series(data)
sf.str.toLowerCase().print()
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
║ 0 │ lower boy            ║
╟───┼──────────────────────╢
║ 1 │ capitals             ║
╟───┼──────────────────────╢
║ 2 │ sentence             ║
╟───┼──────────────────────╢
║ 3 │ swapcase             ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

