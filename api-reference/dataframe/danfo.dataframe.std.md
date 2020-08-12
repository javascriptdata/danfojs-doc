---
description: Return sample standard deviation over requested axis.
---

# DataFrame.std

danfo.DataFrame.**var**\(axis\) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L563)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| axis | Int | 0 for row and 1 for columns  | 1 |

**Returns:**

       ****return **Series**

## **Examples**

## Calculates the standard deviation of values along default axis 1 \(column\)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data)
df.std().print()
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
║ 0 │ 4.69041575982343     ║
╟───┼──────────────────────╢
║ 1 │ 34.23935357645254    ║
╟───┼──────────────────────╢
║ 2 │ 35.103418636936205   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

## Calculates the standard deviation of values along row axis \(0\)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data)
df.std(axis=0).print()
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
║ 0 │ 8.504900548115383    ║
╟───┼──────────────────────╢
║ 1 │ 7.094598884597588    ║
╟───┼──────────────────────╢
║ 2 │ 19.697715603592208   ║
╟───┼──────────────────────╢
║ 3 │ 47.37439533475159    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

## 



