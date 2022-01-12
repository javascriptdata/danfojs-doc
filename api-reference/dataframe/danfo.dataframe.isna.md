---
description: >-
  Return a boolean same-sized object indicating if the values are missing. NaN.
  null and undefined values get mapped to true, and everything else gets mapped
  to false.
---

# DataFrame.isNa

danfo.DataFrame.**isNa**(kwargs)

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [[1, 2, 3], [NaN, 5, 6], [NaN, 30, 40], [39, undefined, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

df.isNa().print()
```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
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
