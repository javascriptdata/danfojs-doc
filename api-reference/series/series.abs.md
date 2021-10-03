---
description: Returns the absolute value in a Series
---

# Series.abs

> danfo.Series.**abs**\(options\)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L793)\]

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameters</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Default</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">options</td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left"><b>inplace</b>: Boolean indicating whether to perform the operation in-place
        or not. Defaults to false</td>
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

let data1 = [-10, 45, 56, -25, 23, -20, 10]
let sf = new dfd.Series(data1)

sf.abs().print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 10                   ║
╟───┼──────────────────────╢
║ 1 │ 45                   ║
╟───┼──────────────────────╢
║ 2 │ 56                   ║
╟───┼──────────────────────╢
║ 3 │ 25                   ║
╟───┼──────────────────────╢
║ 4 │ 23                   ║
╟───┼──────────────────────╢
║ 5 │ 20                   ║
╟───┼──────────────────────╢
║ 6 │ 10                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

