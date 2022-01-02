---
description: Reset the index of a series.
---

# Series.reset\_index

> danfo.series.reset\_index(options) \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L614)]

| Parameters | Type   | Description                                                                                         | Default          |
| ---------- | ------ | --------------------------------------------------------------------------------------------------- | ---------------- |
| options    | Object |  **inplace:** Boolean indicating whether to perform the operation inplace or not. Defaults to false | { inplace:false} |

**Returns :** Series

`reset_index` is useful when the index needs to be treated as a column, or when the index is meaningless and needs to be reset to default, before another operation.

### **Reset index to default values**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
let data = [20, 30, 40]
let sf = new dfd.Series(data, { index: ["a", "b", "c"] })
sf.print()

let sf_reset = sf.reset_index()
sf_reset.print()
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
╔═══╤════╗
║ a │ 20 ║
╟───┼────╢
║ b │ 30 ║
╟───┼────╢
║ c │ 40 ║
╚═══╧════╝

╔═══╤════╗
║ 0 │ 20 ║
╟───┼────╢
║ 1 │ 30 ║
╟───┼────╢
║ 2 │ 40 ║
╚═══╧════╝
```
{% endtab %}
{% endtabs %}

### Reset index to new values in-place

{% tabs %}
{% tab title="Node" %}
```javascript
let data = [1, 2, 3, 4, 5, 6]
let sf = new dfd.Series(data, { index: ['a', 'b', 'c', 'd', 'e', 'f'] })
sf.print()

sf.reset_index({ inplace: true })
sf.print()

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
║ a │ 1 ║
╟───┼───╢
║ b │ 2 ║
╟───┼───╢
║ c │ 3 ║
╟───┼───╢
║ d │ 4 ║
╟───┼───╢
║ e │ 5 ║
╟───┼───╢
║ f │ 6 ║
╚═══╧═══╝

╔═══╤═══╗
║ 0 │ 1 ║
╟───┼───╢
║ 1 │ 2 ║
╟───┼───╢
║ 2 │ 3 ║
╟───┼───╢
║ 3 │ 4 ║
╟───┼───╢
║ 4 │ 5 ║
╟───┼───╢
║ 5 │ 6 ║
╚═══╧═══╝
```
{% endtab %}
{% endtabs %}
