---
description: Return a random sample of items from an axis of object.
---

# Series.sample

> danfo.Series.sample\(num\)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L98)\]

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
      <td style="text-align:left">num</td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">The number of rows to return.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">options</td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left"><b>seed</b>: An integer specifying the random seed that will be used to
        create the distribution. Ensures reproducibility of generated samples.</td>
      <td
      style="text-align:left">
        <p>{</p>
        <p>seed: 1</p>
        <p>}</p>
        </td>
    </tr>
  </tbody>
</table>

**Returns:**

       ****return **{Promies} resolves to Series**

**Example**

```javascript
const dfd = require("danfojs-node")

async function load_data() {
  let data1 = [1, 2, 3, 4, 5, 620, 30, 40, 39, 89, 78];
  let sf1 = new dfd.Series(data1);
  let sample = await sf1.sample(5)
  sample.print()
  
}
load_data()
```

{% tabs %}
{% tab title="Output" %}
```javascript
╔═══╤════╗
║ 2 │ 3  ║
╟───┼────╢
║ 4 │ 5  ║
╟───┼────╢
║ 0 │ 1  ║
╟───┼────╢
║ 7 │ 40 ║
╟───┼────╢
║ 6 │ 30 ║
╚═══╧════╝
```
{% endtab %}
{% endtabs %}

### Specify a seed when sampling

```javascript
const dfd = require("danfojs-node")

async function load_data() {
    let data1 = [1, 2, 3, 4, 5, 620, 30, 40, 39, 89, 78];
    let sf1 = new dfd.Series(data1);
    let sample = await sf1.sample(5, { seed: 2 })
    sample.print()

}
load_data()

```

