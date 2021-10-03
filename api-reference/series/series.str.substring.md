---
description: Obtain the substring of each element in a series
---

# Series.str.substring

> danfo.Series.str.**substring**\(startIndex, endIndex, options\)  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L280)\]

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
      <td style="text-align:left">startIndex</td>
      <td style="text-align:left">Number</td>
      <td style="text-align:left">specify the index to start obtaining the substring</td>
      <td style="text-align:left">0</td>
    </tr>
    <tr>
      <td style="text-align:left">endIndex</td>
      <td style="text-align:left">Number</td>
      <td style="text-align:left">specify the index to end the substring</td>
      <td style="text-align:left">1</td>
    </tr>
    <tr>
      <td style="text-align:left">options</td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left"><b>inplace</b>: Whether to perform the operation in-place or not.</td>
      <td
      style="text-align:left">
        <p>{</p>
        <p><b>inplace</b>: false</p>
        <p>}</p>
        </td>
    </tr>
  </tbody>
</table>

**Returns**

     ****return **Series**

**Example**

Obtain the substring from index 2 to index 4 of the string elements in a Series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower part ', ' CAPITALS city', ' this is a sentence', '  SwAp CaSe']
let sf = new dfd.Series(data)
sf.str.substring(2, 4).print()
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
║ 0 │ we                   ║
╟───┼──────────────────────╢
║ 1 │ AP                   ║
╟───┼──────────────────────╢
║ 2 │ hi                   ║
╟───┼──────────────────────╢
║ 3 │ Sw                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

