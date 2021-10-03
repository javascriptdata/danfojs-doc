---
description: Converts all characters to lower case.
---

# Series.str.toLowerCase

> danfo.Series.str.toLowerCase\(options\)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L20)\]

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

**Example**

Convert all characters in each string element to small letter

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['LOWER BOY', 'CAPITALS', 'SENTENCE', 'SWAPCASE']
let sf = new dfd.Series(data)
sf.str.toLowerCase().print()
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
║ 0 │ lower boy            ║
╟───┼──────────────────────╢
║ 1 │ capitals             ║
╟───┼──────────────────────╢
║ 2 │ sentence             ║
╟───┼──────────────────────╢
║ 3 │ swapcase             ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

