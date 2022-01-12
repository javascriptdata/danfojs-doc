---
description: >-
  Change axis labels. Object values must be unique (1-to-1). Labels not
  contained in a dict / Series will be left as-is. Extra labels listed don’t
  throw an error.
---

# DataFrame.rename

danfo.DataFrame.**rename**(mapper, options)&#x20;

| Parameters  | Type   | Description                                                                                                                                                                  | Default                                                                                   |
| ----------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| **mapper**  | Object | **L**abels and transformations to apply to that axis’ values.                                                                                                                |                                                                                           |
| **options** | Object | <p><strong>axis</strong>: row=0, columns=1.</p><p></p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p> | <p>{</p><p><strong>axis</strong> : 1, </p><p><strong>inplace</strong> : false</p><p>}</p> |

## **Examples**

### Rename columns

By setting **inplace** to _true_, the original DataFrame is modified and nothing is returned. To not modify the original DataFrame and return a new one, set **inplace** to false or leave it as default.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    "A": [-20, 30, 47.3],
    "B": [34, -4, 5],
    "C": [20, 2, 30]
}


let df = new dfd.DataFrame(data)
df.rename({ "A": "new_name" }, { inplace: true })
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
║            │ new_name          │ B                 │ C                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ -20               │ 34                │ 20                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ 30                │ -4                │ 2                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ 47.3              │ 5                 │ 30                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Rename more the one column at time

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20, 30, 47.3],
             "B": [34, -4, 6],
             "C": [20, 2, 30] }


let df = new dfd.DataFrame(data)

df = df.rename({ A: "new_name", C: "new_c" })
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
║   │ new_name          │ B                 │ new_c             ║
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

### Rename index by labels

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    "A": [-20, 30, 47.3],
    "B": [34, -4, 6],
    "C": [20, 2, 30]
}


let df = new dfd.DataFrame(data, { index: ["a", "b", "c"] })
df = df.rename({ "a": 0 }, { axis: 0 })
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
║ b │ 30                │ -4                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 47.3              │ 5                 │ 30                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
