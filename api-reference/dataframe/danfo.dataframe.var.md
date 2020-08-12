---
description: Return unbiased variance over requested axis.
---

# DataFrame.var

danfo.DataFrame.**var**\(axis\) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L563)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| axis | Int | 0 for row and 1 for columns  | 1 |

**Returns:**

       ****return **Series**

## **Examples**

## Calculate variance of values along default axis 1 \(column\)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data)
df.var().print()
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
║ 0 │ 22                   ║
╟───┼──────────────────────╢
║ 1 │ 1172.3333333333333   ║
╟───┼──────────────────────╢
║ 2 │ 1232.25              ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

## Calculate variance of values along row axis \(0\)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data)
df.var(axis=0).print()
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
║ 0 │ 72.33333333333334    ║
╟───┼──────────────────────╢
║ 1 │ 50.33333333333333    ║
╟───┼──────────────────────╢
║ 2 │ 388                  ║
╟───┼──────────────────────╢
║ 3 │ 2244.333333333333    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}





