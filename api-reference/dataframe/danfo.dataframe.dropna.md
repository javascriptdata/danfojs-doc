---
description: Remove missing values (NaNs, undefined) for DataFrame
---

# DataFrame.dropna

danfo.DataFrame.**dropna**(kwargs) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L1430)]

| Parameters | Type   | Description                                                                                                                                                                                                                                                                       | Default                                                                    |
| ---------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| kwargs     | Object | <p>{<strong>axis</strong>: <em>0<strong>: </strong>Apply along</em> row/index axis</p><p><em><strong>             </strong>1</em>: Apply across columns axis</p><p><strong>inplace</strong>:If true, perform operation inplace </p><p>              and return None.</p><p> }</p> | <p>{<strong>axis</strong>: 0, </p><p> <strong>inplace: </strong>false}</p> |

**Returns:**

**       **return** DataFrame**

## **Examples**

### Drop rows (axis=0) with missing values  

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [[1, 2, 3], [NaN, 5, 6], [NaN, 30, 40], [39, undefined, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

df.print()

let df_drop = df.dropna({axis: 0})
df_drop.print()
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
║ 0 │ 1                 │ 2                 │ 3                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Drop columns (axis=1) with missing values  

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [[1, 2, 3], [NaN, 5, 6], [NaN, 30, 40], [39, undefined, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

df.print()

df.dropna({axis: 1, inplace: true})
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
╔═══╤═══════════════════╗
║   │ C                 ║
╟───┼───────────────────╢
║ 0 │ 3                 ║
╟───┼───────────────────╢
║ 1 │ 6                 ║
╟───┼───────────────────╢
║ 2 │ 40                ║
╟───┼───────────────────╢
║ 3 │ 78                ║
╚═══╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
