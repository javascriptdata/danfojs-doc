---
description: Apply custom aggregate function to grouped data
---

# Groupby.apply

danfo.Groupby.**apply**\(callable\) \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs-node/src/core/groupby.js#L297)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| callable | Function \| function to be applied to grouped data | Undefined |  |

**Returns:**

       ****return **DataFrame**

## **Examples**

Using apply to create a custom function that subtract the minimum value of each grouped data from each of its values

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
      'A': ['foo', 'bar', 'foo', 'bar',

        'foo', 'bar', 'foo', 'foo'],

      'B': ['one', 'one', 'two', 'three',

        'two', 'two', 'one', 'three'],

      'C': [1, 3, 2, 4, 5, 2, 6, 7],

      'D': [3, 2, 4, 1, 5, 6, 7, 8]
    };
let df = new dfd.DataFrame(data);
let group_df = df.groupby(["A", "B"]);

const subMin = (x) => {
  return x.sub(x.min());
};

group_df.apply(subMin).print();

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
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C_apply           │ D_apply           ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ one               │ 5                 │ 4                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ foo               │ two               │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ foo               │ two               │ 3                 │ 1                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ foo               │ three             │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 5 │ bar               │ one               │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 6 │ bar               │ two               │ 0                 │ 0                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 7 │ bar               │ three             │ 0                 │ 0                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

\*\*\*\*
