---
description: Assign new Index to Series
---

# Series.set\_index

> danfo.series.**set\_index\(**options**\)** \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L635)\]

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Default</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">index</td>
      <td style="text-align:left">Array</td>
      <td style="text-align:left">new index values</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">options</td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">inplace: Boolean indicating whether to perform the operation inplace or
        not. Defaults to false</td>
      <td style="text-align:left">
        <p>{</p>
        <p>inplace: false</p>
        <p>}</p>
      </td>
    </tr>
  </tbody>
</table>

**Returns:** Series

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
```text
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
```text
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
```text
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

