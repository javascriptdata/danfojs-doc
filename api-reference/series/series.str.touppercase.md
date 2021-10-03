---
description: Converts all characters to uppercase.
---

# Series.str.toUpperCase

> danfo.Series.str.toUpperCase\(options\)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L33)\]

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

Convert all characters in each string element to capital letter

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower boy', 'CAPITALS', 'sentence', 'SwApCaSe']
let sf = new dfd.Series(data)
sf.str.toUpperCase().print()
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
║ 0 │ LOWER BOY            ║
╟───┼──────────────────────╢
║ 1 │ CAPITALS             ║
╟───┼──────────────────────╢
║ 2 │ SENTENCE             ║
╟───┼──────────────────────╢
║ 3 │ SWAPCASE             ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

