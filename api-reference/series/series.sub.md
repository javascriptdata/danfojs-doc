---
description: Return Subtraction of series and other, element-wise (binary operator sub).
---

# Series.sub

> danfo.Series.sub(other, options)&#x20;

| Parameters | Type          | Description                                                                                    | Default                               |
| ---------- | ------------- | ---------------------------------------------------------------------------------------------- | ------------------------------------- |
| other      | Series\|int\| | values                                                                                         |                                       |
| options    | Object        | inplace: Boolean indicating whether to perform the operation inplace or not. Defaults to false | <p>{</p><p>inplace: false</p><p>}</p> |

**Return:** Series

**Example**

subtract from values of another series

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [30, 40, 3, 5]
let data2 = [1, 2, 3, 4]
let sf1 = new dfd.Series(data1)
let sf2 = new dfd.Series(data2)
sf1.sub(sf2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 29                   ║
╟───┼──────────────────────╢
║ 1 │ 38                   ║
╟───┼──────────────────────╢
║ 2 │ 0                    ║
╟───┼──────────────────────╢
║ 3 │ 1                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

subtract from a value

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [1, 2, 3, 4, 5]
let sf1 = new dfd.Series(data1)

sf1.sub(2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ -1                   ║
╟───┼──────────────────────╢
║ 1 │ 0                    ║
╟───┼──────────────────────╢
║ 2 │ 1                    ║
╟───┼──────────────────────╢
║ 3 │ 2                    ║
╟───┼──────────────────────╢
║ 4 │ 3                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
