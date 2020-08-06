---
description: Return the median of the values for the requested axis.
---

# DataFrame.median

danfo.DataFrame.**median**\(axis\) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L474)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| axis | Int | 0 for row and 1 for columns  | 1 |

**Returns:**

       ****return **Series**

## **Examples**

## Calculates the median of values along default axis 1 \(column\)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
cols = ["A", "B", "C"]

df.print()

let df = new dfd.DataFrame(data)
df.median().print()
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
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 11                │ 20                │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 15                │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 2                 │ 89                │ 78                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝

╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ A │ 2                    ║
╟───┼──────────────────────╢
║ B │ 25                   ║
╟───┼──────────────────────╢
║ C │ 23                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

## Calculates the median of values along row axis \(0\)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
cols = ["A", "B", "C"]

df.print()
let df = new dfd.DataFrame(data)
df.median(axis=0).print()
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
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 11                │ 20                │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 15                │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 2                 │ 89                │ 78                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝

╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 11                   ║
╟───┼──────────────────────╢
║ 1 │ 6                    ║
╟───┼──────────────────────╢
║ 2 │ 30                   ║
╟───┼──────────────────────╢
║ 3 │ 78                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

