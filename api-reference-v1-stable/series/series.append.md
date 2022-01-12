---
description: Add a new value or values to the end of a Series.
---

# Series.append

danfo.Series.**append**(newValue, index, options) \[[source](https://github.com/opensource9ja/danfojs/blob/e25010c26d9c423412613d820015a48ad03d5c6d/danfojs-node/src/core/series.js#L1120)]

| Parameters | Type          | Description                                                                                                                | Default |
| ---------- | ------------- | -------------------------------------------------------------------------------------------------------------------------- | ------- |
| newValue   | Array, Series | Object to append                                                                                                           |         |
| index      | Array         | The new index value(s) to append to the Series. Must contain the same number of values as `newValues` as they map `1 - 1`. |         |
| options    | Object        | <p>{ <br><strong>inplace</strong>: Whether to perform operation in-place or not.</p><p>}</p>                               | false   |

**Returns:**

&#x20;      ****       return **Series**

****

### **Append new Series to the end of a Series**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let sf1 = new dfd.Series([1, 2, 3, 4], { index: ['f1', 'f2', 'f3', 'f4'] })
let sf2 = new dfd.Series(["a", "b", "c"])

new_sf = sf1.append(sf2, ["f5", "f6", "f7"])
new_sf.print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔════╤═══╗
║ f1 │ 1 ║
╟────┼───╢
║ f2 │ 2 ║
╟────┼───╢
║ f3 │ 3 ║
╟────┼───╢
║ f4 │ 4 ║
╟────┼───╢
║ f5 │ a ║
╟────┼───╢
║ f6 │ b ║
╟────┼───╢
║ f7 │ c ║
╚════╧═══╝
```
{% endtab %}
{% endtabs %}

### **Append new Series to the end of a Series in-place**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let sf1 = new dfd.Series([1, 2, 3, 4], { index: ['f1', 'f2', 'f3', 'f4'] })
let sf2 = new dfd.Series(["a", "b", "c"])
let newIndex = ["f5", "f6", "f7"]

sf1.append(sf2, newIndex, { inplace: true })
sf1.print()
```
{% endtab %}
{% endtabs %}

```
╔════╤═══╗
║ f1 │ 1 ║
╟────┼───╢
║ f2 │ 2 ║
╟────┼───╢
║ f3 │ 3 ║
╟────┼───╢
║ f4 │ 4 ║
╟────┼───╢
║ f5 │ a ║
╟────┼───╢
║ f6 │ b ║
╟────┼───╢
║ f7 │ c ║
╚════╧═══╝
```

### **Append an array to the end of Series**

{% tabs %}
{% tab title="Node" %}
```javascript
let sf1 = new dfd.Series([1, 2, 3, 4], { index: ['f1', 'f2', 'f3', 'f4'] })
let sfArr = ["a", "b", "c"]

new_sf = sf1.append(sfArr, ["f5", "f6", "f7"])
new_sf.print()

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
╔════╤═══╗
║ f1 │ 1 ║
╟────┼───╢
║ f2 │ 2 ║
╟────┼───╢
║ f3 │ 3 ║
╟────┼───╢
║ f4 │ 4 ║
╟────┼───╢
║ f5 │ a ║
╟────┼───╢
║ f6 │ b ║
╟────┼───╢
║ f7 │ c ║
╚════╧═══╝

```
{% endtab %}
{% endtabs %}
