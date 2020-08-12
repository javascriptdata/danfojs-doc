---
description: >-
  Obtain the substring from a String element in a Series, by specifying the
  number of string to obtain starting from a specific index.
---

# Series.str.substr

> danfo.Series.str.substr\(startIndex, num\)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L265)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| startIndex | Number | specify the index to start obtaining the substring | 0 |
| num | Number | The number of character to obtain starting from the startIndex | 1 |

**Returns:**

      ****return Series

**Example**

Obtain substring\( containing 4 characters\) starting from the third character \(2nd index\).

```javascript
const dfd = require("danfojs-node")

let data = ['lower part ', ' CAPITALS city', ' this is a sentence', '  SwAp CaSe']
let sf = new dfd.Series(data)
sf.str.substr(2, 4).print()
```

{% tabs %}
{% tab title="Output" %}
```javascript
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ wer                  ║
╟───┼──────────────────────╢
║ 1 │ APIT                 ║
╟───┼──────────────────────╢
║ 2 │ his                  ║
╟───┼──────────────────────╢
║ 3 │ SwAp                 ║
╚═══╧══════════════════════╝

```
{% endtab %}
{% endtabs %}

