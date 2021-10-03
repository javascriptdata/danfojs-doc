---
description: Replace values given in replace param with value
---

# Series.replace

> danfo.Series.**replace**\(options\)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L892)\]

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
        <p> <b>oldValue</b>: The value you want to replace</p>
        <p><b>newValue</b>: The new value you want to replace the old value with</p>
        <p><b>inplace</b>: Boolean indicating whether to perform the operation inplace
          or not</p>
      </td>
      <td style="text-align:left">
        <p>{</p>
        <p>inplace: false</p>
        <p>}</p>
      </td>
    </tr>
  </tbody>
</table>

**Returns**: Series

**Examples**

### Replace a value in a series and return a new series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf = new dfd.Series(data1)
let sf_rep = sf.replace({ oldValue: 10, newValue: -50 })

sf_rep.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤═════╗
║ 0 │ -50 ║
╟───┼─────╢
║ 1 │ 45  ║
╟───┼─────╢
║ 2 │ 56  ║
╟───┼─────╢
║ 3 │ 25  ║
╟───┼─────╢
║ 4 │ 23  ║
╟───┼─────╢
║ 5 │ 20  ║
╟───┼─────╢
║ 6 │ -50 ║
╚═══╧═════╝

```
{% endtab %}
{% endtabs %}

### Replace a value in-place

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf = new dfd.Series(data1)
sf.replace({ oldValue: 10, newValue: -50, inplace: true})

sf.print()
```
{% endtab %}
{% endtabs %}

```text
╔═══╤═════╗
║ 0 │ -50 ║
╟───┼─────╢
║ 1 │ 45  ║
╟───┼─────╢
║ 2 │ 56  ║
╟───┼─────╢
║ 3 │ 25  ║
╟───┼─────╢
║ 4 │ 23  ║
╟───┼─────╢
║ 5 │ 20  ║
╟───┼─────╢
║ 6 │ -50 ║
╚═══╧═════╝

```

