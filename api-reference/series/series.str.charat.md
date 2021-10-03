---
description: Obtain the character at the specified index (position)
---

# Series.str.charAt

> danfo.Series.str.**charAt**\(index\)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L64)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| index | int | the index at which to obtain the character | 0 |

**Returns**:  Series \(Character element\)

**Example**

Obtain the character at index 2 of all string elements in the series.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower boy', 'CAPITALS', 'sentence', 'SwApCaSe']
let sf = new dfd.Series(data)
sf.str.charAt(2).print()
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
║ 0 │ w                    ║
╟───┼──────────────────────╢
║ 1 │ P                    ║
╟───┼──────────────────────╢
║ 2 │ n                    ║
╟───┼──────────────────────╢
║ 3 │ A                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

