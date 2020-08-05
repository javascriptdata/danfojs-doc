---
description: Replace a word or character(s) in a String element
---

# Series.str.replace

> danfo.Series.str.replace\(searchValue, replaceValue\)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L191)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| searchValue | string | the string to search for | "" |
| replaceValue | String | string to replace the searched string | "" |

**Returns:** Series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

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
```text
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

