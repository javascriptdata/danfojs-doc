---
description: Reset the index of the DataFrame, and use the default one instead.
---

# DataFrame.reset_index

danfo.DataFrame.**reset_index**(options) \[[source](https://github.com/opensource9ja/danfojs/blob/cf5c7ae3a009458e61eedd18d9c9b5b6b10d5276/danfojs/src/core/frame.js#L125)]

| Parameters | Type   | Description                                                                                                                                                                | Default          |
| ---------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------- |
| options    | Object | <p><strong>{ </strong></p><p><strong>inplace</strong>: sBoolean indicating whether to perform the operation inplace or not. Defaults to false</p><p><strong>}</strong></p> | {inplace: false} |

**Returns:**

**       **return** DataFrame**

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20, 30, 47.3],
             "B": [34, -4, 5, 6],
             "C": [20, 2, 3, 30] }


let df = new dfd.DataFrame(data, {index: ["a", "b", "a"]})
df.print()

df.reset_index(true) //inplace
//df = df.reset_index() //not in inplace

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

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ a │ -20               │ 34                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ b │ 30                │ -4                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ a │ 47.3              │ 5                 │ 30                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


 //after reseting index

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ -20               │ 34                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 30                │ -4                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 47.3              │ 5                 │ 30                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
