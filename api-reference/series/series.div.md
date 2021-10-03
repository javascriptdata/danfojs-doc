---
description: >-
  Return Floating division of series and other, element-wise (binary operator
  truediv).
---

# Series.div

> danfo.Series.div\(other, options\)  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L188)\]

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
      <td style="text-align:left">other</td>
      <td style="text-align:left">Series|int|</td>
      <td style="text-align:left">values</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">options</td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">inplace: Boolean indicating whether to perform the operation inplace or
        not. Defaults to false</td>
      <td style="text-align:left">
        <p>{</p>
        <p>inplace: false</p>
        <p>}</p>
      </td>
    </tr>
  </tbody>
</table>

**Return:** Series

**Example**

divide with values of another series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [30, 40, 3, 5]
let data2 = [1, 2, 3, 4]
let sf1 = new dfd.Series(data1)
let sf2 = new dfd.Series(data2)
sf1.div(sf2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 30                   ║
╟───┼──────────────────────╢
║ 1 │ 20                   ║
╟───┼──────────────────────╢
║ 2 │ 1                    ║
╟───┼──────────────────────╢
║ 3 │ 1.25                 ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

### divide with a value

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [1, 2, 3, 4, 5]
let sf1 = new dfd.Series(data1)

sf1.div(2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 0.5                  ║
╟───┼──────────────────────╢
║ 1 │ 1                    ║
╟───┼──────────────────────╢
║ 2 │ 1.5                  ║
╟───┼──────────────────────╢
║ 3 │ 2                    ║
╟───┼──────────────────────╢
║ 4 │ 2.5                  ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

