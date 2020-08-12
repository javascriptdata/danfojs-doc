---
description: >-
  Obtain the position of the last found occurrence of a specified value in a
  string
---

# Series.str.lastIndexOf

danfo.Series.str.lastIndexOf\(str\)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L175)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| str | string | the string to search for | "" |

**Returns**: Series

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower', 'CAPITALS', 'this is a sentence', 'SwApCaSe']
let sf = new dfd.Series(data)
sf.str.lastIndexOf("r").print()
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
║ 0 │ 4                    ║
╟───┼──────────────────────╢
║ 1 │ -1                   ║
╟───┼──────────────────────╢
║ 2 │ -1                   ║
╟───┼──────────────────────╢
║ 3 │ -1                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}



