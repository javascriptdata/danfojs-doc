---
description: Remove missing values from Series
---

# Series.dropna

> danfo.Series.**dropna**\(options\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L931)\]

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
      <td style="text-align:left">inplace: Boolean indicating whether to perform the operation inplace or
        not. Defaults to false</td>
      <td style="text-align:left">
        <p>{
          <br />inplace: false</p>
        <p>}</p>
      </td>
    </tr>
  </tbody>
</table>

**Returns**: Series

**Examples**

### Drop all nan value and then return New Series.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, undefined, 10, 23, 20, undefined, 10]
let sf = new dfd.Series(data1)
let sf_rep = sf.dropna()

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
║ 0 │ 10                   ║
╟───┼──────────────────────╢
║ 1 │ 45                   ║
╟───┼──────────────────────╢
║ 3 │ 10                   ║
╟───┼──────────────────────╢
║ 4 │ 23                   ║
╟───┼──────────────────────╢
║ 5 │ 20                   ║
╟───┼──────────────────────╢
║ 7 │ 10                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

### Drop nan values in-place

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, undefined, 10, 23, 20, undefined, 10]
let sf = new dfd.Series(data1)
sf.dropna({inplace:true})

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
║ 0 │ 10                   ║
╟───┼──────────────────────╢
║ 1 │ 45                   ║
╟───┼──────────────────────╢
║ 3 │ 10                   ║
╟───┼──────────────────────╢
║ 4 │ 23                   ║
╟───┼──────────────────────╢
║ 5 │ 20                   ║
╟───┼──────────────────────╢
║ 7 │ 10                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

