---
description: >-
  Return the inferred column types in the DataFrame. This returns a Series with
  the data type of each column. The result’s index is the original DataFrame’s
  columns.
---

# DataFrame.ctypes

danfo.DataFrame.**dtypes** \[[source](https://github.com/opensource9ja/danfojs/blob/eb5919d2cac34271fc3b725fa24aa3ad4eacde37/danfojs/src/core/frame.js#L1848)\]

**Returns:**

       ****return  **Series**

## **Examples**

Returns auto-generated ****index of a ****DataFrame

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"A": [-20.1, 30, 47.3, -20],
            "B": [34, -4, 5, 6], 
            "C": [20, -20, 30, -40]}

let df = new dfd.DataFrame(data)

df.ctypes.print()
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
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ A │ float32              ║
╟───┼──────────────────────╢
║ B │ int32                ║
╟───┼──────────────────────╢
║ C │ int32                ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

Columns with mixed types are represented as **string.**

{% tabs %}
{% tab title="Node" %}
```javascript

const dfd = require("danfojs-node")

let data = {"A": [-20.1, 30, 47.3, -20],
            "B": [34, -4, 5, 6], 
            "C": [20, -20, 30, -40],
            "D": ["a", "b", 20, 2.5]}
            
let df = new dfd.DataFrame(data)

df.ctypes.print()
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
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ A │ float32              ║
╟───┼──────────────────────╢
║ B │ int32                ║
╟───┼──────────────────────╢
║ C │ int32                ║
╟───┼──────────────────────╢
║ D │ string               ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

**Note**: To cast a type, use the [astype](dataframe.astype.md) method. 

