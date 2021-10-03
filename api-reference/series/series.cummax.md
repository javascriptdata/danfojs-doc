---
description: Returns cumulative maximum over a series
---

# Series.cummax

> danfo.Series.**cummax**\(options\)\[[source](https://github.com/opensource9ja/danfojs/blob/e25010c26d9c423412613d820015a48ad03d5c6d/danfojs-node/src/core/series.js#L730)\]

<table>
  <thead>
    <tr>
      <th style="text-align:left">options</th>
      <th style="text-align:left">Object</th>
      <th style="text-align:left">
        <p><b>inplace</b>: Whether to perform operation in-place or not.</p>
        <p></p>
      </th>
      <th style="text-align:left">{
        <br /><b>inplace</b>: false
        <br />}</th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf1 = new dfd.Series(data1)

sf1.cummax().print()
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
║ 3 │ 56                   ║
╟───┼──────────────────────╢
║ 4 │ 56                   ║
╟───┼──────────────────────╢
║ 5 │ 56                   ║
╟───┼──────────────────────╢
║ 6 │ 56                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

