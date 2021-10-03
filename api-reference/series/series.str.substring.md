---
description: Obtain the substring of each element in a series
---

# Series.str.substring

> danfo.Series.str.**substring**\(startIndex, endIndex\)  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L280)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| startIndex | Number | specify the index to start obtaining the substring | 0 |
| endIndex | Number | specify the index to end the substring | 1 |

**Returns**

     ****return **Series**

**Example**

Obtain the substring from index 2 to index 4 of the string elements in a Series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower part ', ' CAPITALS city', ' this is a sentence', '  SwAp CaSe']
let sf = new dfd.Series(data)
sf.str.substring(2, 4).print()
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
║ 0 │ we                   ║
╟───┼──────────────────────╢
║ 1 │ AP                   ║
╟───┼──────────────────────╢
║ 2 │ hi                   ║
╟───┼──────────────────────╢
║ 3 │ Sw                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

