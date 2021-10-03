---
description: Join a new string value to all string elements in a Series.
---

# Series.str.join

> danfo.Series.str.**join**\(valToJoin, joinChar, options\)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L308)\]

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
      <td style="text-align:left">valToJoin</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">the string value you want to</td>
      <td style="text-align:left">&quot;&quot;</td>
    </tr>
    <tr>
      <td style="text-align:left">joinChar</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">The delimiter to specify the joining</td>
      <td style="text-align:left">&quot; &quot;</td>
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

**Returns:**

   ****return **Series**

**Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = ['lower part', 'CAPITALS city', 'this is a sentence', 'SwAp CaSe']
let sf = new dfd.Series(data)
sf.str.join("new", "_").print()
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
╔═══╤════════════════════════╗
║ 0 │ lower part_new         ║
╟───┼────────────────────────╢
║ 1 │ CAPITALS city_new      ║
╟───┼────────────────────────╢
║ 2 │ this is a sentence_new ║
╟───┼────────────────────────╢
║ 3 │ SwAp CaSe_new          ║
╚═══╧════════════════════════╝
```
{% endtab %}
{% endtabs %}

