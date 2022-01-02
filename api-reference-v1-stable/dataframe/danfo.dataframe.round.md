---
description: Round elements in a DataFrame to a specified number of decimal places.
---

# DataFrame.round

danfo.DataFrame.**round**(options) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L454)]

| Parameters | Type   | Description                                                                                        | Default            |
| ---------- | ------ | -------------------------------------------------------------------------------------------------- | ------------------ |
| dp         | Int    | Number of decimal places to round to. Defaults to 1                                                | 1                  |
| options    | Object | **inplace:** Boolean indicating whether to perform the operation inplace or not. Defaults to false | { inplace: false } |

**Returns:**

**       **return** DataFrame**

## **Examples**

## Round elements to 1dp (Default)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

data = [[11.20, 20.1234, 3.567], [1, 15.1, 6.0], [2, 3.09, 40.234]]
cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
df.print()

let new_df = df.round()

new_df.print()
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
║ 0 │ 11.2              │ 20.1234           │ 3.567             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 15.1              │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 3.09              │ 40.234            ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


 //after round

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 11.2              │ 20.1              │ 3.6               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 15.1              │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 3.1               │ 40.2              ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

## Round elements to a specified number of decimal places

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

data = [[11.20, 20.1234, 3.567], [1, 15.1, 6.0], [2, 3.09, 40.234]]
cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
df.print()

let new_df = df.round(2)

new_df.print()
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
║ 0 │ 11.2              │ 20.1234           │ 3.567             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 15.1              │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 3.09              │ 40.234            ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


 //after round operation 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 11.2              │ 20.12             │ 3.57              ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 15.1              │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 3.09              │ 40.23             ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

##
