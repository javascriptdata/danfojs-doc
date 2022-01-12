---
description: Remove duplicate rows
---

# Series.dropDuplicates

> danfo.Series.dropDuplicates(options)&#x20;

| Parameters | Type   | Description       | Default                                                                                                                                                                                |
| ---------- | ------ | ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| options    | Object | **keep**: "first" | <p>"last", which duplicate value to keep. Defaults to "first".<br><strong>inplace</strong>: Boolean indicating whether to perform the operation in-place or not. Defaults to false</p> |

**Returns:** Series

**Examples**

### Drop duplicate by keeping the first occurrence of the duplicate value

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, 56, 10, 23, 20, 10, 10]
let sf = new dfd.Series(data1)
let sf_drop = sf.dropDuplicates()

sf_drop.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤════╗
║ 0 │ 10 ║
╟───┼────╢
║ 1 │ 45 ║
╟───┼────╢
║ 2 │ 56 ║
╟───┼────╢
║ 4 │ 23 ║
╟───┼────╢
║ 5 │ 20 ║
╚═══╧════╝
```
{% endtab %}
{% endtabs %}

### Drop duplicate and keep only the last duplicated value

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, 56, 10, 23, 20, 10, 10]
let sf = new dfd.Series(data1)
let sf_drop = sf.dropDuplicates({ keep: "last" })

sf_drop.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤════╗
║ 1 │ 45 ║
╟───┼────╢
║ 2 │ 56 ║
╟───┼────╢
║ 4 │ 23 ║
╟───┼────╢
║ 5 │ 20 ║
╟───┼────╢
║ 7 │ 10 ║
╚═══╧════╝
```
{% endtab %}
{% endtabs %}

### Remove duplicate value in-place

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = ["A", "A", "A", "B", "B", "C", "C", "D"]
let sf = new dfd.Series(data1)
sf.dropDuplicates({ inplace: true })

sf.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤═══╗
║ 0 │ A ║
╟───┼───╢
║ 3 │ B ║
╟───┼───╢
║ 5 │ C ║
╟───┼───╢
║ 7 │ D ║
╚═══╧═══╝
```
{% endtab %}
{% endtabs %}
