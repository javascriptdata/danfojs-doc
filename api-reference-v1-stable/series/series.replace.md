---
description: Replace values given in replace param with value
---

# Series.replace

> danfo.Series.**replace**(options)    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L892)]

| Parameters | Type   | Description                                                                                                                                                                                                                                               | Default                               |
| ---------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------- |
| options    | Object | <p> <strong>oldValue</strong>: The value you want to replace</p><p><strong>newValue</strong>: The new value you want to replace the old value with</p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not</p> | <p>{</p><p>inplace: false</p><p>}</p> |

**Returns**: Series

**Examples**

### Replace a value in a series and return a new series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf = new dfd.Series(data1)
let sf_rep = sf.replace({ oldValue: 10, newValue: -50 })

sf_rep.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤═════╗
║ 0 │ -50 ║
╟───┼─────╢
║ 1 │ 45  ║
╟───┼─────╢
║ 2 │ 56  ║
╟───┼─────╢
║ 3 │ 25  ║
╟───┼─────╢
║ 4 │ 23  ║
╟───┼─────╢
║ 5 │ 20  ║
╟───┼─────╢
║ 6 │ -50 ║
╚═══╧═════╝

```
{% endtab %}
{% endtabs %}

### Replace a value in-place

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf = new dfd.Series(data1)
sf.replace({ oldValue: 10, newValue: -50, inplace: true})

sf.print()
```
{% endtab %}
{% endtabs %}

```
╔═══╤═════╗
║ 0 │ -50 ║
╟───┼─────╢
║ 1 │ 45  ║
╟───┼─────╢
║ 2 │ 56  ║
╟───┼─────╢
║ 3 │ 25  ║
╟───┼─────╢
║ 4 │ 23  ║
╟───┼─────╢
║ 5 │ 20  ║
╟───┼─────╢
║ 6 │ -50 ║
╚═══╧═════╝

```
