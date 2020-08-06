---
description: Makes a new copy of the DataFrame
---

# DataFrame.copy

danfo.DataFrame.**copy**\(\) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L940)\]

**Returns:**

       ****return **new DataFrame**

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
let data = [{"A": [-20.1, 30, 47.3, -20]},
            {"B": [34, -4, 5, 6]}, 
             {"C": [20, -20, 30, -40]}]
let df = new dfd.DataFrame(data)
let new_df = df.copy()
new_df.print()
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
║ 0 │ -20.1             │ 34                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 30                │ -4                │ -20               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 47.3              │ 5                 │ 30                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ -20               │ 6                 │ -40               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝

```
{% endtab %}
{% endtabs %}



