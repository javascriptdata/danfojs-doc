---
description: >-
  Change axes labels. Object values must be unique (1-to-1). Labels not
  contained in a dict / Series will be left as-is. Extra labels listed don’t
  throw an error.
---

# DataFrame.rename

danfo.DataFrame.**rename**(kwargs) \[[source](https://github.com/opensource9ja/danfojs/blob/cf5c7ae3a009458e61eedd18d9c9b5b6b10d5276/danfojs/src/core/frame.js#L125)]

| Parameters | Type   | Description                                                                                                                                                                                                                                                                                | Default                          |
| ---------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------- |
| options    | Object | <p>{</p><p><strong>mapper</strong>:  Object of labels and transformations to apply to that axis’ values.</p><p><strong>axis</strong>:  row=0, columns=1.</p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p><p>}</p> | {**axis**: 1, **inplace:**false} |

**Returns:**

&#x20;      ****       return **DataFrame**

## **Examples**

### Rename columns&#x20;

By setting **inplace** to _true_, the original DataFrame is modified and nothing is returned. To not modify the original DataFrame and return a new one, set **inplace** to false or leave it as default.&#x20;

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20, 30, 47.3],
             "B": [34, -4, 5],
             "C": [20, 2, 30] }


let df = new dfd.DataFrame(data)
df.rename({ mapper: {"A": "new_name"},inplace: true })
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
║   │ new_name          │ B                 │ C                 ║
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

### Rename more the one column at time

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20, 30, 47.3],
             "B": [34, -4, 6],
             "C": [20, 2, 30] }


let df = new dfd.DataFrame(data)
df = df.rename({ mapper: {"A": "new_name", "C": "new_c"}})
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
df = df.rename({ mapper: { "a": 0 }, axis: 0 })
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
