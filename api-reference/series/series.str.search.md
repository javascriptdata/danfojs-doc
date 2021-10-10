---
description: Obtain the index position of a searched  character in a String
---

# Series.str.search

> danfo.Series.str.**search**(str, options)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L220)]



| Parameters | Type   | Description                                                     | Default                                                |
| ---------- | ------ | --------------------------------------------------------------- | ------------------------------------------------------ |
| str        | String | the string to search for                                        | ""                                                     |
| options    | Object | **inplace**: Whether to perform the operation in-place or not.  | <p>{</p><p><strong>inplace</strong>: false</p><p>}</p> |

**Returns:**

**     **return Series: Series of index position

**Example**

obtain the index position for a character

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower part ', ' CAPITALS city', ' this is a sentence', '  SwAp CaSe']
let sf = new dfd.Series(data)
sf.str.search("S").print()
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
║ 0 │ -1                   ║
╟───┼──────────────────────╢
║ 1 │ 8                    ║
╟───┼──────────────────────╢
║ 2 │ -1                   ║
╟───┼──────────────────────╢
║ 3 │ 2                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

Obtain the index position for a searched word

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower city ', ' CAPITALS city', ' this is a sentence', '  SwAp CaSe']
let sf = new dfd.Series(data)
sf.str.search("city").print()
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
║ 0 │ 6                    ║
╟───┼──────────────────────╢
║ 1 │ 10                   ║
╟───┼──────────────────────╢
║ 2 │ -1                   ║
╟───┼──────────────────────╢
║ 3 │ -1                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
