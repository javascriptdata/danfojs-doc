---
description: >-
  Obtain the substring from a String element in a Series, by specifying the
  number of string to obtain starting from a specific index.
---

# Series.str.substr

> danfo.Series.str.substr\(startIndex, num, options\)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L265)\]

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
      <td style="text-align:left">num</td>
      <td style="text-align:left">Number</td>
      <td style="text-align:left">The number of character to obtain starting from the startIndex</td>
      <td
      style="text-align:left">1</td>
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

      ****return Series

**Example**

Obtain substring\( containing 4 characters\) starting from the third character \(2nd index\).

```javascript
const dfd = require("danfojs-node")

let data = ['lower part ', ' CAPITALS city', ' this is a sentence', '  SwAp CaSe']
let sf = new dfd.Series(data)
sf.str.substr(2, 4).print()
```

{% tabs %}
{% tab title="Output" %}
```javascript
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ wer                  ║
╟───┼──────────────────────╢
║ 1 │ APIT                 ║
╟───┼──────────────────────╢
║ 2 │ his                  ║
╟───┼──────────────────────╢
║ 3 │ SwAp                 ║
╚═══╧══════════════════════╝

```
{% endtab %}
{% endtabs %}

