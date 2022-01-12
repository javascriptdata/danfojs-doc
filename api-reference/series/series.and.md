---
description: >-
  Returns the logical AND between Series and other. Supports element wise
  operations and broadcasting.
---

# Series.and

> danfo.Series.and(other)&#x20;

| Parameters | Type                             | Description          | Default |
| ---------- | -------------------------------- | -------------------- | ------- |
| other      | Series, Scalar, Array of Scalars | Data to compare with |         |

**Return:** Series

### **Logical AND between two Series object**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [false, false, false, true, false, false, true];
let data2 = [false, false, false, false, false, false, true];

let sf = new dfd.Series(data1);
let sf2 = new dfd.Series(data2);
let res = sf.and(sf2)
res.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤═══════╗
║ 0 │ false ║
╟───┼───────╢
║ 1 │ false ║
╟───┼───────╢
║ 2 │ false ║
╟───┼───────╢
║ 3 │ false ║
╟───┼───────╢
║ 4 │ false ║
╟───┼───────╢
║ 5 │ false ║
╟───┼───────╢
║ 6 │ true  ║
╚═══╧═══════╝
```
{% endtab %}
{% endtabs %}

### **Logical AND between Series and Array of the same length**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [false, false, false, true, false, false, true];
let data2 = [false, false, false, false, false, false, true];

let sf = new dfd.Series(data1);
let res = sf.and(data2)
res.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤═══════╗
║ 0 │ false ║
╟───┼───────╢
║ 1 │ false ║
╟───┼───────╢
║ 2 │ false ║
╟───┼───────╢
║ 3 │ false ║
╟───┼───────╢
║ 4 │ false ║
╟───┼───────╢
║ 5 │ false ║
╟───┼───────╢
║ 6 │ true  ║
╚═══╧═══════╝
```
{% endtab %}
{% endtabs %}

### **Logical AND between a Series and single value with broadcasting**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
let data1 = [false, false, false, true, false, false, true];

let sf = new dfd.Series(data1);
let res = sf.and(false)
res.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤═══════╗
║ 0 │ false ║
╟───┼───────╢
║ 1 │ false ║
╟───┼───────╢
║ 2 │ false ║
╟───┼───────╢
║ 3 │ false ║
╟───┼───────╢
║ 4 │ false ║
╟───┼───────╢
║ 5 │ false ║
╟───┼───────╢
║ 6 │ false ║
╚═══╧═══════╝
```
{% endtab %}
{% endtabs %}
