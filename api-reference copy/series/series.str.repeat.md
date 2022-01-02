---
description: Repeat the the character(s) in a string for a specified number of time
---

# Series.str.repeat

> danfo.Series.str.**repeat**(num, options)  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L205)]

| Parameters | Type    | Description                                                     | Default                                                |
| ---------- | ------- | --------------------------------------------------------------- | ------------------------------------------------------ |
| num        | integer | the string to search for                                        | 1                                                      |
| options    | Object  | **inplace**: Whether to perform the operation in-place or not.  | <p>{</p><p><strong>inplace</strong>: false</p><p>}</p> |

**Returns:**  Series

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

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
```
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
