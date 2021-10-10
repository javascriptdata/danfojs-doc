---
description: Sort a Dataframe in ascending or descending order by a specified column name.
---

# DataFrame.sort_values

danfo.DataFrame.**sort_values**(kwargs) \[[source](https://github.com/opensource9ja/danfojs/blob/cf5c7ae3a009458e61eedd18d9c9b5b6b10d5276/danfojs/src/core/frame.js#L125)]

| Parameters | Type   | Description                                                                                                                                                                                                                                                                                                                      | Default                                  |
| ---------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------- |
| options    | Object | <p>{</p><p><strong>by</strong>:  This key can be either a single column name or a single array of the same length as the calling DataFrame,</p><p><strong>ascending: </strong>Order of sorting</p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p><p>}</p> | {**ascending**: true, **inplace:**false} |

**Returns:**

**       **return** DataFrame**

## **Examples**

### **Sort DataFrame by a column in ascending order**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20, 30, 47.3],
             "B": [34, -4, 5, 6],
             "C": [20, 2, 3, 30] }


let df = new dfd.DataFrame(data)
df.sort_values({by: "C", inplace: true})
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
║ 0 │ 30                │ -4                │ 2                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 47.3              │ 5                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ -20               │ 34                │ 20                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### **Sort DataFrame by a column in descending order**

{% tabs %}
{% tab title="Node" %}
```javascript

const dfd = require("danfojs-node")

let data = { "A": [-20, 30, 47.3],
             "B": [34, -4, 5, 6],
             "C": [20, 2, 3, 30] }


let df = new dfd.DataFrame(data)
df.sort_values({by: "B", inplace: true, ascending: false})
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
║ 0 │ -20               │ 34                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 47.3              │ 5                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 30                │ -4                │ 2                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
