---
description: Return a cumulative sum of a series
---

# Series.cumsum

> danfo.Series.**cumsum**\(options\) \[[source](https://github.com/opensource9ja/danfojs/blob/e25010c26d9c423412613d820015a48ad03d5c6d/danfojs-node/src/core/series.js#L713)\]

<table>
  <thead>
    <tr>
      <th style="text-align:left">options</th>
      <th style="text-align:left">Object</th>
      <th style="text-align:left">
        <p><b>inplace</b>: Whether to perform operation in-place or not.</p>
        <p></p>
      </th>
      <th style="text-align:left">{
        <br /><b>inplace</b>: false
        <br />}</th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf1 = new dfd.Series(data1)

sf1.cumsum().print()
```
{% endtab %}

{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.jsdelivr.net/npm/danfojs@0.2.4/dist/index.min.js"></script>
    <title>Document</title>
</head>

<body>

    <script>

      //danfo is exposed on dfd namespace 
      s = new dfd.Series([1,2,3,4,5]) 

    </script>

</body>

</html>
```
{% endtab %}
{% endtabs %}

```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 10                   ║
╟───┼──────────────────────╢
║ 1 │ 55                   ║
╟───┼──────────────────────╢
║ 2 │ 111                  ║
╟───┼──────────────────────╢
║ 3 │ 136                  ║
╟───┼──────────────────────╢
║ 4 │ 159                  ║
╟───┼──────────────────────╢
║ 5 │ 179                  ║
╟───┼──────────────────────╢
║ 6 │ 189                  ║
╚═══╧══════════════════════╝
```

