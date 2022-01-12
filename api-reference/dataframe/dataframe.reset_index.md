---
description: Resets the index of the DataFrame, and use the default one instead.
---

# DataFrame.resetIndex

danfo.DataFrame.resetIndex(options)

| Parameters | Type   | Description                                                                                                                                                              | Default               |
| ---------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------- |
| options    | Object | <p><strong>{</strong></p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p><p><strong>}</strong></p> | { **inplace**: false} |

**Returns:**

\*\*\*\* return **DataFrame**

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    "A": [-20, 30, 47.3],
    "B": [34, 5, 6],
    "C": [20, 3, 30]
}


let df = new dfd.DataFrame(data, { index: ["a", "b", "c"] })
df.print()

df.resetIndex({ inplace: true }) //inplace
//df = df.resetIndex() //not in inplace

df.print()
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
║            │ A                 │ B                 │ C                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ a          │ -20               │ 34                │ 20                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ b          │ 30                │ 5                 │ 3                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ c          │ 47.3              │ 6                 │ 30                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ -20               │ 34                │ 20                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ 30                │ 5                 │ 3                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ 47.3              │ 6                 │ 30                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
