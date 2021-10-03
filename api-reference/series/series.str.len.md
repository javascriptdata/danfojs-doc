---
description: Obtain the length of each string element in a Series
---

# Series.str.len

> danfo.Series.str.**len**\(options\) \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L324)\]

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

**Examples**

Returns the length \(number of character\) of a string, and also return the length \(number of elements\) of Array

{% tabs %}
{% tab title="JavaScript" %}
```javascript
const dfd = require("danfojs-node")

let data = ["dog", 5,"cat","fog","mug","animals"]
let sf = new dfd.Series(data)
sf.str.len().print()
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
╔═══╤═══╗
║ 0 │ 3 ║
╟───┼───╢
║ 1 │ 1 ║
╟───┼───╢
║ 2 │ 3 ║
╟───┼───╢
║ 3 │ 3 ║
╟───┼───╢
║ 4 │ 3 ║
╟───┼───╢
║ 5 │ 7 ║
╚═══╧═══╝
```
{% endtab %}
{% endtabs %}

