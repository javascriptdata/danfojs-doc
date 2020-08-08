---
description: Remove duplicate rows
---

# Series.drop\_duplicates

> danfo.Series.**drop\_duplicates**\(kwargs\)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L1007)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| kwargs\["**inplace**"\] | bool | return a new series or not.  | false |
| kwargs\["**keep**"\] | String | {"**first**"or "**last**"}. Specify if to keep the last or the first duplicate value  | first |

**Returns:** Series

**Examples**

Drop duplicate by keep the first value of the duplicate value

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [10, 45, 56, 10, 23, 20, 10, 10]
let sf = new dfd.Series(data1)
let sf_drop = sf.drop_duplicates()

sf_drop.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 10                   ║
╟───┼──────────────────────╢
║ 1 │ 45                   ║
╟───┼──────────────────────╢
║ 2 │ 56                   ║
╟───┼──────────────────────╢
║ 4 │ 23                   ║
╟───┼──────────────────────╢
║ 5 │ 20                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

Drop duplicate and keep only the last duplicated value

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = [10, 45, 56, 10, 23, 20, 10, 10]
let sf = new dfd.Series(data1)
let sf_drop = sf.drop_duplicates({keep:"last"})

sf_drop.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 1 │ 45                   ║
╟───┼──────────────────────╢
║ 2 │ 56                   ║
╟───┼──────────────────────╢
║ 4 │ 23                   ║
╟───┼──────────────────────╢
║ 5 │ 20                   ║
╟───┼──────────────────────╢
║ 7 │ 10                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

Remove duplicate value in series without returning a new series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data1 = ["A", "A", "A", "B", "B", "C", "C", "D"]
let sf = new dfd.Series(data1)
sf.drop_duplicates({inplace:true})

sf.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ A                    ║
╟───┼──────────────────────╢
║ 3 │ B                    ║
╟───┼──────────────────────╢
║ 5 │ C                    ║
╟───┼──────────────────────╢
║ 7 │ D                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

