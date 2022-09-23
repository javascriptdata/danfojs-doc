---
description: Sort a Dataframe in ascending or descending order by a specified column name.
---

# DataFrame.sortValues

danfo.DataFrame.**sortValues**(by, options) \[[source](https://github.com/opensource9ja/danfojs/blob/cf5c7ae3a009458e61eedd18d9c9b5b6b10d5276/danfojs/src/core/frame.js#L125)]

| Parameters | Type   | Description                                                                                                                                                                                                              | Default                                                                                  |
| ---------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------- |
| **by**     | Object | This key can be either a single column name or a single array of the same length as the calling DataFrame.                                                                                                               |                                                                                          |
| options    | Object | <p>Optional configuratio<strong>n:</strong></p><p><strong>ascending:</strong> Order of sorting</p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p> | <p>{</p><p><strong>ascending</strong>: true, <strong>inplace</strong>: false</p><p>}</p> |

## **Examples**

### **Sort DataFrame by a column in ascending order**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    "A": [-20, 30, 47.3],
    "B": [34, 5, 6],
    "C": [20, 3, 30]
}


let df = new dfd.DataFrame(data)
df.sortValues("C", { inplace: true })
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
║ 1          │ 30                │ 5                 │ 3                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ -20               │ 34                │ 20                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ 47.3              │ 6                 │ 30                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### **Sort DataFrame by a column in descending order**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20, 30, 47.3],
             "B": [34, 5, 6],
             "C": [20, 3, 30] }



let df = new dfd.DataFrame(data)
df.sortValues("C", { ascending: false, inplace: true })
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
║ 0          │ 47.3              │ 6                 │ 30                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ -20               │ 34                │ 20                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ 30                │ 5                 │ 3                 ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
