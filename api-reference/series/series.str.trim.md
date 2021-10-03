---
description: Remove leading and trailing Whitespace from a String element
---

# Series.str.trim

> danfo.Series.str.**trim**\(options\)  **\[**[**source**](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L293)**\]**

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

**Returns:**

         ****return Series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower part ', ' CAPITALS city', ' this is a sentence', '  SwAp CaSe']
let sf = new dfd.Series(data)
sf.str.trim().print()
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
║ 0 │ lower part           ║
╟───┼──────────────────────╢
║ 1 │ CAPITALS city        ║
╟───┼──────────────────────╢
║ 2 │ this is a sentence   ║
╟───┼──────────────────────╢
║ 3 │ SwAp CaSe            ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

