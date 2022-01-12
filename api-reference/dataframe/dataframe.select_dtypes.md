---
description: Return a subset of the DataFrame’s columns based on the column dtypes.
---

# DataFrame.selectDtypes

danfo.DataFrame.selectDtypes()

| Parameters | Type  | Description                     | Default |
| ---------- | ----- | ------------------------------- | ------- |
| include    | Array | List of column dtypes to return |         |

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"A": [-20.1, 30, 47.3, -20],
            "B": [34, -4, 5, 6], 
            "C": [20, -20, 30, -40],
            "D": ["a", "b", 20, 2.5]}
            
let df = new dfd.DataFrame(data)


float_df = df.selectDtypes(['float32'])
float_df.print()

mix_df = df.selectDtypes(['float32', "int32"])
mix_df.print()

str_df = df.selectDtypes(['string'])
str_df.print()
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
//select float column(s)
╔═══╤══════════════════════╗
║   │ A                    ║
╟───┼──────────────────────╢
║ 0 │ -20.1                ║
╟───┼──────────────────────╢
║ 1 │ 30                   ║
╟───┼──────────────────────╢
║ 2 │ 47.3                 ║
╟───┼──────────────────────╢
║ 3 │ -20                  ║
╚═══╧══════════════════════╝


 //select both float and int columns

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

//return string type column
╔═══╤══════════════════════╗
║   │ D                    ║
╟───┼──────────────────────╢
║ 0 │ a                    ║
╟───┼──────────────────────╢
║ 1 │ b                    ║
╟───┼──────────────────────╢
║ 2 │ 20                   ║
╟───┼──────────────────────╢
║ 3 │ 2.5                  ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
