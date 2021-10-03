---
description: Repeat the the character(s) in a string for a specified number of time
---

# Series.str.repeat

> danfo.Series.str.**repeat**\(num, options\)  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L205)\]

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
      <td style="text-align:left">num</td>
      <td style="text-align:left">integer</td>
      <td style="text-align:left">the string to search for</td>
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
```text
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

