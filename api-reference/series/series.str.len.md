---
description: Obtain the length of each string element in a Series
---

# Series.str.len

> danfo.Series.str.**len**\(\) \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L324)\]

**Parameters**: None

**Returns:**

      return Series

**Examples**

Returns the length \(number of character\) of a string, and also return the length \(number of elements\) of Array

{% tabs %}
{% tab title="JavaScript" %}
```javascript
const dfd = require("danfojs-node")

let data = ["dog", 5,"cat",["fog","mug"],"animals"]
let sf = new dfd.Series(data)
sf.str.len().print()
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
║ 0 │ 3                    ║
╟───┼──────────────────────╢
║ 1 │ NaN                  ║
╟───┼──────────────────────╢
║ 2 │ 3                    ║
╟───┼──────────────────────╢
║ 3 │ 2                    ║
╟───┼──────────────────────╢
║ 4 │ 7                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

