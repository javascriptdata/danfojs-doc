---
description: Capitalize the first character of each string
---

# Series.str.capitalize

> danfo.Series.str.**capitalize**\(options\)       \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L46)\]

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

**Returns**:  Series \(String element\)

**Example**

Convert  the first character of a string to capital letter

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower boy', 'capitals', 'sentence', 'swApCaSe']
let sf = new dfd.Series(data)
sf.str.capitalize().print()
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
║ 0 │ Lower boy            ║
╟───┼──────────────────────╢
║ 1 │ Capitals             ║
╟───┼──────────────────────╢
║ 2 │ Sentence             ║
╟───┼──────────────────────╢
║ 3 │ Swapcase             ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

