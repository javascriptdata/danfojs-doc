---
description: round off floating values in series
---

# Series.round

> danfo.Series.round\(dp, options\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L404)\]

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
      <td style="text-align:left">dp</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">decimal place to round off to</td>
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

let data1 = [30.21091, 40.190901, 3.564, 5.0212]
let sf1 = new dfd.Series(data1)

sf1.round(2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 30.21                ║
╟───┼──────────────────────╢
║ 1 │ 40.19                ║
╟───┼──────────────────────╢
║ 2 │ 3.56                 ║
╟───┼──────────────────────╢
║ 3 │ 5.02                 ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}



