---
description: Capitalize the first character of each string
---

# Series.str.capitalize

> danfo.Series.str.**capitalize**\(\)       \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L46)\]

**Parameters:** None

**Returns**:  Series \(String element\)

**Example**

Convert  the first character of a string to capital letter

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower boy', 'capitals', 'sentence', 'swApCaSe']
let sf = new dfd.Series(data)
sf.str.capitalize().print()
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
║ 0 │ Lower boy            ║
╟───┼──────────────────────╢
║ 1 │ Capitals             ║
╟───┼──────────────────────╢
║ 2 │ Sentence             ║
╟───┼──────────────────────╢
║ 3 │ Swapcase             ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

