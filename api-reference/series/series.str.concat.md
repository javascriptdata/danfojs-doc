---
description: Joins two or more strings/arrays
---

# Series.str.concat

> danfo.Series.str.**concat**(other, position, options)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L80)]

| Parameters | Type            | Description                                                                                                                                                                                  | Default                                                |
| ---------- | --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| other      | string or Array | string or list of strings to add to each string element of the series                                                                                                                        | ""                                                     |
| position   | Int             | The position to add the **other **(string or array) is either 0 or 1. 0 is to add the other at the beginning of each of the string element, and 1 is to add to the end of the string element | 1                                                      |
| options    | Object          | **inplace**: Whether to perform the operation in-place or not.                                                                                                                               | <p>{</p><p><strong>inplace</strong>: false</p><p>}</p> |

**Returns: **Series (String element)

**Examples**

Add the strings from an Array to the start of each of the String element in Series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower boy', 'CAPITALS', 'sentence', 'SwApCaSe']
let data2 = ['XX', 'YY', 'BB', '01']
let sf = new dfd.Series(data)
sf.str.concat(data2,0).print()
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
║ 0 │ XXlower boy          ║
╟───┼──────────────────────╢
║ 1 │ YYCAPITALS           ║
╟───┼──────────────────────╢
║ 2 │ BBsentence           ║
╟───┼──────────────────────╢
║ 3 │ 01SwApCaSe           ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

Add the strings from an Array to the end of each of the String element in Series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower boy', 'CAPITALS', 'sentence', 'SwApCaSe']
let data2 = ['XX', 'YY', 'BB', '01']
let sf = new dfd.Series(data)
sf.str.concat(data2,1).print()
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
║ 0 │ lower boyXX          ║
╟───┼──────────────────────╢
║ 1 │ CAPITALSYY           ║
╟───┼──────────────────────╢
║ 2 │ sentenceBB           ║
╟───┼──────────────────────╢
║ 3 │ SwApCaSe01           ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

Add a string to the start of each string element in a Series

{% tabs %}
{% tab title="Output" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower boy', 'CAPITALS', 'sentence', 'SwApCaSe']
let data2 = ['XX', 'YY', 'BB', '01']
let sf = new dfd.Series(data)
sf.str.concat("pre",0).print()
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
║ 0 │ prelower boy         ║
╟───┼──────────────────────╢
║ 1 │ preCAPITALS          ║
╟───┼──────────────────────╢
║ 2 │ presentence          ║
╟───┼──────────────────────╢
║ 3 │ preSwApCaSe          ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

Add a string to the end of each string element in a series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower boy', 'CAPITALS', 'sentence', 'SwApCaSe']
let data2 = ['XX', 'YY', 'BB', '01']
let sf = new dfd.Series(data)
sf.str.concat("post",1).print()
```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

```
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ lower boypost        ║
╟───┼──────────────────────╢
║ 1 │ CAPITALSpost         ║
╟───┼──────────────────────╢
║ 2 │ sentencepost         ║
╟───┼──────────────────────╢
║ 3 │ SwApCaSepost         ║
╚═══╧══════════════════════╝
```
