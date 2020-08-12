---
description: Join a new string value to all string elements in a Series.
---

# Series.str.join

> danfo.Series.str.**join**\(valToJoin,joinChar\)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L308)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| valToJoin | String | the string value you want to  |  "" |
| joinChar | String | The delimiter to specify the joining | " " |

**Returns:**

   ****return **Series**

**Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower part', 'CAPITALS city', 'this is a sentence', 'SwAp CaSe']
let sf = new dfd.Series(data)
sf.str.join("new", "_").print()
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
║ 0 │ lower part_new       ║
╟───┼──────────────────────╢
║ 1 │ CAPITALS city_new    ║
╟───┼──────────────────────╢
║ 2 │ this is a sentenc... ║
╟───┼──────────────────────╢
║ 3 │ SwAp CaSe_new        ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

