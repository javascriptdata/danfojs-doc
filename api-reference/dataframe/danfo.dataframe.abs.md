---
description: Return a DataFrame with the absolute numeric value of each element.
---

# DataFrame.abs

danfo.DataFrame.**sum**(options)

| Parameters | Type   | Description                                                                                        | Default            |
| ---------- | ------ | -------------------------------------------------------------------------------------------------- | ------------------ |
| options    | Object | **inplace:** Boolean indicating whether to perform the operation inplace or not. Defaults to false | { inplace: false } |

## **Examples**

The abs function only works on numeric columns and will throw an error if string columns are found in the DataFrame.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
let data = {"A": [-20.1, 30, 47.3, -20],
            "B": [34, -4, 5, 6], 
             "C": [20, -20, 30, -40]}
             
let df = new dfd.DataFrame(data)

df.print()

let df_abs = df.abs()
df_abs.abs().print()
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
║ 0 │ -20.1             │ 34                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 30                │ -4                │ -20               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 47.3              │ 5                 │ 30                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ -20               │ 6                 │ -40               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝

//after applying abs function

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 20.1              │ 34                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 30                │ 4                 │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 47.3              │ 5                 │ 30                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 20                │ 6                 │ 40                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
