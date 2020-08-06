---
description: Returns array of index with missing values
---

# DataFrame.nanindex

danfo.DataFrame.**nanindex**\(\) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L1410)\]

**Returns:**

       ****return **Array**

## **Examples**

### Drop rows \(axis=0\) with missing values  

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [[1, 2, 3], [NaN, 5, 6], [NaN, 30, 40], [39, undefined, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

df.print()

console.log(df.nanIndex());
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
║ 0 │ 1                 │ 2                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ NaN               │ 5                 │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ NaN               │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 39                │ NaN               │ 78                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝

[ 1, 2, 3 ]
```
{% endtab %}
{% endtabs %}

