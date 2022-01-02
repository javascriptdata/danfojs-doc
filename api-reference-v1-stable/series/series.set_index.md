---
description: Assign new Index to Series
---

# Series.set_index

> danfo.series.**set_index(**options**) **\[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L635)]

| Parameter | Type   | Description                                                                                    | Default                               |
| --------- | ------ | ---------------------------------------------------------------------------------------------- | ------------------------------------- |
| index     | Array  | new index values                                                                               |                                       |
| options   | Object | inplace: Boolean indicating whether to perform the operation inplace or not. Defaults to false | <p>{</p><p>inplace: false</p><p>}</p> |

**Returns: **Series

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
let data = [{ alpha: "A", count: 1 }, { alpha: "B", count: 2 }, { alpha: "C", count: 3 }]
let sf = new dfd.Series(data)
sf.print()

let sf_new = sf.set_index({ "index": ["one", "two", "three"] })
sf_new.print()
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
╔═══╤═════════════════════════╗
║ 0 │ {"alpha":"A","count":1} ║
╟───┼─────────────────────────╢
║ 1 │ {"alpha":"B","count":2} ║
╟───┼─────────────────────────╢
║ 2 │ {"alpha":"C","count":3} ║
╚═══╧═════════════════════════╝

╔═══════╤═════════════════════════╗
║ one   │ {"alpha":"A","count":1} ║
╟───────┼─────────────────────────╢
║ two   │ {"alpha":"B","count":2} ║
╟───────┼─────────────────────────╢
║ three │ {"alpha":"C","count":3} ║
╚═══════╧═════════════════════════╝
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ["Humans","Life","Meaning","Fact","Truth"]
let sf = new dfd.Series(data)
let sf_new = sf.set_index({ "index": ["H", "L", "M","F","T"] })
sf_new.print()
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
║ H │ Humans               ║
╟───┼──────────────────────╢
║ L │ Life                 ║
╟───┼──────────────────────╢
║ M │ Meaning              ║
╟───┼──────────────────────╢
║ F │ Fact                 ║
╟───┼──────────────────────╢
║ T │ Truth                ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

### Set index in-place

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [1, 2, 3, 4, 5, 6]
let sf = new dfd.Series(data)
sf.set_index({ index: ["one", "two", "three", "four", "five", "six"], inplace: true })
sf.print()
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
╔═══════╤═══╗
║ one   │ 1 ║
╟───────┼───╢
║ two   │ 2 ║
╟───────┼───╢
║ three │ 3 ║
╟───────┼───╢
║ four  │ 4 ║
╟───────┼───╢
║ five  │ 5 ║
╟───────┼───╢
║ six   │ 6 ║
╚═══════╧═══╝

```
{% endtab %}
{% endtabs %}
