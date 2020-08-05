---
description: Repeat the the character(s) in a string for a specified number of time
---

# Series.str.repeat

> danfo.Series.str.**repeat**\(num\)  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L205)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| num | integer | the string to search for | 1 |

**Returns:**  Series

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = ['a', 'b', 'c', 'd']
let sf = new dfd.Series(data)
sf.str.repeat(4).print()
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
║ 0 │ aaaa                 ║
╟───┼──────────────────────╢
║ 1 │ bbbb                 ║
╟───┼──────────────────────╢
║ 2 │ cccc                 ║
╟───┼──────────────────────╢
║ 3 │ dddd                 ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

