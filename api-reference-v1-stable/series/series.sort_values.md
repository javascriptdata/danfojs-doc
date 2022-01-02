---
description: Sorts a Series in ascending or descending order
---

# Series.sort_values

> danfo.Series.sort_values(options)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L511)]

| Parameters | Type   | Description                                                                                                                                                                                                                           | Default                                                   |
| ---------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| options    | Object | <p><strong>inplace</strong>: Boolean indicating whether to perform the operation in-place or not. Defaults to false</p><p><strong>ascending</strong>: Whether to return sorted values in ascending order or not. Defaults to true</p> | <p>{<br>ascending: true,</p><p>inplace: false</p><p>}</p> |

  **Return:** Series

### Sort values in a Series 

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [20, 30, 1, 2, 4, 57, 89, 0, 4]
let sf1 = new dfd.Series(data1)
let sf2 = sf1.sort_values()

sf2.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤════╗
║ 7 │ 0  ║
╟───┼────╢
║ 2 │ 1  ║
╟───┼────╢
║ 3 │ 2  ║
╟───┼────╢
║ 8 │ 4  ║
╟───┼────╢
║ 4 │ 4  ║
╟───┼────╢
║ 0 │ 20 ║
╟───┼────╢
║ 1 │ 30 ║
╟───┼────╢
║ 5 │ 57 ║
╟───┼────╢
║ 6 │ 89 ║
╚═══╧════╝
```
{% endtab %}
{% endtabs %}

### Sort Series in-place

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [20, 30, 1, 2, 4, 57, 89, 0, 4]
let sf1 = new dfd.Series(data1)
sf1.sort_values({ inplace: true })

sf1.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤════╗
║ 7 │ 0  ║
╟───┼────╢
║ 2 │ 1  ║
╟───┼────╢
║ 3 │ 2  ║
╟───┼────╢
║ 8 │ 4  ║
╟───┼────╢
║ 4 │ 4  ║
╟───┼────╢
║ 0 │ 20 ║
╟───┼────╢
║ 1 │ 30 ║
╟───┼────╢
║ 5 │ 57 ║
╟───┼────╢
║ 6 │ 89 ║
╚═══╧════╝

```
{% endtab %}
{% endtabs %}

Sort Series values in descending order

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [20, 30, 1, 2, 4, 57, 89, 0, 4]
let sf1 = new dfd.Series(data1)
sf1.sort_values({ "ascending": false, "inplace": true })

sf1.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤════╗
║ 6 │ 89 ║
╟───┼────╢
║ 5 │ 57 ║
╟───┼────╢
║ 1 │ 30 ║
╟───┼────╢
║ 0 │ 20 ║
╟───┼────╢
║ 4 │ 4  ║
╟───┼────╢
║ 8 │ 4  ║
╟───┼────╢
║ 3 │ 2  ║
╟───┼────╢
║ 2 │ 1  ║
╟───┼────╢
║ 7 │ 0  ║
╚═══╧════╝
```
{% endtab %}
{% endtabs %}
