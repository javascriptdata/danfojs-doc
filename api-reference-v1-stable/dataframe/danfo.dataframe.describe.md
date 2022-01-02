---
description: >-
  Generate descriptive statistics for each numeric column. Numeric columns are
  of type Int and float.
---

# DataFrame.describe

danfo.DataFrame.**describe**() \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L821)]

**Returns:**

&#x20;      ****       return **DataFrame**

## **Examples**

Descriptive statistics include those that summarize the central tendency, dispersion and shape of a dataset’s distribution, excluding `NaN` values.&#x20;

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
let data = [[0, 2, 4, "a"], [360, 180, 360, "b"], [2, 4, 6, "c"]]
let col_names = ["col1", "col2", "col3", "col4"]
let df = new dfd.DataFrame(data, {columns: col_names})

df.describe().print()
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
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ col1              │ col2              │ col3              ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ count      │ 3                 │ 3                 │ 3                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ mean       │ 120.66666666666…  │ 62                │ 123.33333333333…  ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ std        │ 207.27115895206…  │ 102.19589032832…  │ 204.961785055979  ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ min        │ 0                 │ 2                 │ 4                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ median     │ 2                 │ 4                 │ 6                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ max        │ 360               │ 180               │ 360               ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ variance   │ 42961.333333333…  │ 10444             │ 42009.333333333…  ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

##
