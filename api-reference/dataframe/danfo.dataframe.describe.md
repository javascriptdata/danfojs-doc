---
description: >-
  Generate descriptive statistics for each numeric column. Numeric columns are
  of type Int and float.
---

# DataFrame.describe

danfo.DataFrame.**describe**\(\) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L821)\]

**Returns:**

       ****return **DataFrame**

## **Examples**

Descriptive statistics include those that summarize the central tendency, dispersion and shape of a dataset’s distribution, excluding `NaN` values. 

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
```text
╔══════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║          │ col1              │ col2              │ col3              ║
╟──────────┼───────────────────┼───────────────────┼───────────────────╢
║ count    │ 3                 │ 3                 │ 3                 ║
╟──────────┼───────────────────┼───────────────────┼───────────────────╢
║ mean     │ 120.666664        │ 62                │ 123.333336        ║
╟──────────┼───────────────────┼───────────────────┼───────────────────╢
║ std      │ 207.271159        │ 102.19589         │ 204.961785        ║
╟──────────┼───────────────────┼───────────────────┼───────────────────╢
║ min      │ 0                 │ 2                 │ 4                 ║
╟──────────┼───────────────────┼───────────────────┼───────────────────╢
║ median   │ 2                 │ 4                 │ 6                 ║
╟──────────┼───────────────────┼───────────────────┼───────────────────╢
║ max      │ 360               │ 180               │ 360               ║
╟──────────┼───────────────────┼───────────────────┼───────────────────╢
║ variance │ 42961.333333      │ 10444             │ 42009.333333      ║
╚══════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

## 

