---
description: Replace all NaN value with specified value
---

# Series.fillna

> danfo.Series.**fillna**\(options\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L470)\]

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
      <td style="text-align:left">
        <p><b>value</b>: The value to replace all missing value with.</p>
        <p><b>inplace</b>: Boolean indicating whether to perform the operation inplace
          or not. Defaults to false</p>
      </td>
      <td style="text-align:left">
        <p>{</p>
        <p>inplace: false</p>
        <p>}</p>
      </td>
    </tr>
  </tbody>
</table>

**Examples**

### Fill nan value and then return new series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [NaN, 1, 2, 33, 4, NaN, 5, 6, 7, 8]
let sf = new dfd.Series(data1)

let sf_rep = sf.fillna({ value: -999})

sf_rep.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ -999                 ║
╟───┼──────────────────────╢
║ 1 │ 1                    ║
╟───┼──────────────────────╢
║ 2 │ 2                    ║
╟───┼──────────────────────╢
║ 3 │ 33                   ║
╟───┼──────────────────────╢
║ 4 │ 4                    ║
╟───┼──────────────────────╢
║ 5 │ -999                 ║
╟───┼──────────────────────╢
║ 6 │ 5                    ║
╟───┼──────────────────────╢
║ 7 │ 6                    ║
╟───┼──────────────────────╢
║ 8 │ 7                    ║
╟───┼──────────────────────╢
║ 9 │ 8                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

### Fill nan value in-place

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [NaN, 1, 2, 33, 4, NaN, 5, 6, 7, 8]
let sf = new dfd.Series(data1)
sf.fillna({ value: -999, inplace: true })

sf.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ -999                 ║
╟───┼──────────────────────╢
║ 1 │ 1                    ║
╟───┼──────────────────────╢
║ 2 │ 2                    ║
╟───┼──────────────────────╢
║ 3 │ 33                   ║
╟───┼──────────────────────╢
║ 4 │ 4                    ║
╟───┼──────────────────────╢
║ 5 │ -999                 ║
╟───┼──────────────────────╢
║ 6 │ 5                    ║
╟───┼──────────────────────╢
║ 7 │ 6                    ║
╟───┼──────────────────────╢
║ 8 │ 7                    ║
╟───┼──────────────────────╢
║ 9 │ 8                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

