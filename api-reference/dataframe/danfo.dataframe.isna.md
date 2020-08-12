---
description: >-
  Return a boolean same-sized object indicating if the values are NaN.
  NaN/undefined values gets mapped to true values, and everything else gets
  mapped to false values.
---

# DataFrame.isna

danfo.DataFrame.**isna**\(kwargs\) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L1350)\]

**Returns:**

       ****return **DataFrame**

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [[1, 2, 3], [NaN, 5, 6], [NaN, 30, 40], [39, undefined, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

df.isna().print()

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
║ 0 │ false             │ false             │ false             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ true              │ false             │ false             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ true              │ false             │ false             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ false             │ true              │ false             ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

