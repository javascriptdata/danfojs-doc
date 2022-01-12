---
description: Returns the number of unique elements in a column, across the specified axis.
---

# DataFrame.nUnique

danfo.DataFrame.nUnique(axis) \[[source](https://github.com/opensource9ja/danfojs/blob/f84d7f53f2b0639e464f9483fb5cea969ad913d6/danfojs/src/core/frame.js#L1975)]

| Parameters | Type | Description                           | Default |
| ---------- | ---- | ------------------------------------- | ------- |
| axis       | Int  | 0 for row axis, and 1 for column axis | 1       |

## **Examples**

### Return number of unique values along default axis (axis=1)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20, 30, 47.3, -20] ,
             "B": [34, -4, 5, 6] ,
             "C": [20, 20, 30, 30],
             "D": ["a", "b", "c", "c"] }

let df = new dfd.DataFrame(data)
df.nunique().print()
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
╔═══╤═══╗
║ 0 │ 4 ║
╟───┼───╢
║ 1 │ 4 ║
╟───┼───╢
║ 2 │ 4 ║
╟───┼───╢
║ 3 │ 4 ║
╚═══╧═══╝
```
{% endtab %}
{% endtabs %}

### Return number of unique values in row axis (axis=0)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20, 30, 47.3, -20] ,
             "B": [34, -4, 5, 6] ,
             "C": [20, 20, 30, 30],
             "D": ["a", "b", "c", "c"] }

let df = new dfd.DataFrame(data)
df.nUnique(axis=0).print()
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
╔═══╤═══╗
║ A │ 3 ║
╟───┼───╢
║ B │ 4 ║
╟───┼───╢
║ C │ 2 ║
╟───┼───╢
║ D │ 3 ║
╚═══╧═══╝
```
{% endtab %}
{% endtabs %}

**Note:** To get the unique elements along an axis, see [DataFrame.unique.](dataframe.nunique-1.md)
