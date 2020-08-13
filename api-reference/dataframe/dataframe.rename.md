---
description: >-
  Change axes labels. Object values must be unique (1-to-1). Labels not
  contained in a dict / Series will be left as-is. Extra labels listed don’t
  throw an error.
---

# DataFrame.rename

danfo.DataFrame.**rename**\(kwargs\) \[[source](https://github.com/opensource9ja/danfojs/blob/cf5c7ae3a009458e61eedd18d9c9b5b6b10d5276/danfojs/src/core/frame.js#L125)\]

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
      <td style="text-align:left">kwargs</td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">
        <p>{</p>
        <p><b>mapper</b>: Object of labels and transformations to apply to that axis&#x2019;
          values.</p>
        <p><b>axis</b>: row=0, columns=1.</p>
        <p><b>inplace</b>: specify whether to perform the operation to the row/column
          with/without creating a new DataFrame</p>
        <p>}</p>
      </td>
      <td style="text-align:left">{<b>axis</b>: 1, <b>inplace:</b>false}</td>
    </tr>
  </tbody>
</table>

**Returns:**

       ****return **DataFrame**

## **Examples**

### Rename columns 

By setting **inplace** to _true_, the original DataFrame is modified and nothing is returned. To not modify the original DataFrame and return a new one, set **inplace** to false or leave it as default. 

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20, 30, 47.3],
             "B": [34, -4, 5],
             "C": [20, 2, 3, 30] }


let df = new dfd.DataFrame(data)
df.rename({ mapper: {"A": "new_name"},inplace: true })
df.print()
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
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ new_name          │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ -20               │ 34                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 30                │ -4                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 47.3              │ 5                 │ 30                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Rename more the one column at time

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20, 30, 47.3],
             "B": [34, -4, 5, 6],
             "C": [20, 2, 3, 30] }


let df = new dfd.DataFrame(data)
df = df.rename({ mapper: {"A": "new_name", "C": "new_c"}})
df.print()

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

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ new_name          │ B                 │ new_c             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ -20               │ 34                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 30                │ -4                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 47.3              │ 5                 │ 30                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Rename index by labels

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20, 30, 47.3],
             "B": [34, -4, 5, 6],
             "C": [20, 2, 3, 30] }


let df = new dfd.DataFrame(data, {index: ["a", "b", "a"]})
df = df.rename({ mapper: {"a": 0}, axis: 0})
df.print()

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

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ -20               │ 34                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ b │ 30                │ -4                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 47.3              │ 5                 │ 30                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

