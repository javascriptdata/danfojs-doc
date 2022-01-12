---
description: Replace values given in replace param with value
---

# Series.replace

> danfo.Series.**replace**(oldValue, newValue, options)&#x20;

| Parameters   | Type   | Description                                                                       | Default                               |
| ------------ | ------ | --------------------------------------------------------------------------------- | ------------------------------------- |
| **oldValue** | Any    | <p>The value you want to replace.</p><p> </p>                                     |                                       |
| **newValue** | Any    | The new value you want to replace with.                                           |                                       |
| options      | Object | **inplace**: Boolean, indicating whether to perform the operation inplace or not. | <p>{</p><p>inplace: false</p><p>}</p> |

**Returns**: Series

**Examples**

### Replace a value in a series and return a new series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf = new dfd.Series(data1)
let sf_rep = sf.replace(10, -50)

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
sf.replace(10, -50, { inplace: true})

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
