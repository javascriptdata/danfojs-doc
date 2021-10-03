---
description: Obtain the character at the specified index (position)
---

# Series.str.charAt

> danfo.Series.str.**charAt**\(index\)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L64)\]

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
      <td style="text-align:left">index</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">the index at which to obtain the character</td>
      <td style="text-align:left">0</td>
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

**Returns**:  Series \(Character element\)

**Example**

Obtain the character at index 2 of all string elements in the series.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower boy', 'CAPITALS', 'sentence', 'SwApCaSe']
let sf = new dfd.Series(data)
sf.str.charAt(2).print()
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
║ 0 │ w                    ║
╟───┼──────────────────────╢
║ 1 │ P                    ║
╟───┼──────────────────────╢
║ 2 │ n                    ║
╟───┼──────────────────────╢
║ 3 │ A                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

