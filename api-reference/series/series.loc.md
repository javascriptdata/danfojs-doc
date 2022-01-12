---
description: Access a group of rows by label(s) or a boolean array.
---

# Series.loc

danfo.Series.**loc**()&#x20;

| Parameters | Type          | Description                                                            | Default |
| ---------- | ------------- | ---------------------------------------------------------------------- | ------- |
| rows       | Array, String | Array, string slice, index of row positions boolean mask to filter by. |         |

## **Examples**

`.loc()` is label position based (from `0` to `length-1` of the row axis).

Allowed inputs are:

* An integer, e.g. `"r1"`.
* A list or array of integers, e.g. `["a", "b", "d"]`.
* A boolean mask. E.g \[ true, false, false ]
* A string slice object with ints, e.g. `[`'`"a":"d"'], ["1:4"]`

_**Note:** only \*\*\*\* the start label is included, and the end label is ignored._

`.loc` will raise a `ValueEror` if a requested label is not found.

### **Indexing by specific row index**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


const data = [12, 34, 2.2, 2, 30, 30, 2.1, 7]
const index = ["a", "b", "c", "d", "e", "f", "g", "h"]
let s = new dfd.Series(data, { index })
s.print()

s.loc(["a", "g"]).print()
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
╔═══╤═════╗
║ a │ 12  ║
╟───┼─────╢
║ b │ 34  ║
╟───┼─────╢
║ c │ 2.2 ║
╟───┼─────╢
║ d │ 2   ║
╟───┼─────╢
║ e │ 30  ║
╟───┼─────╢
║ f │ 30  ║
╟───┼─────╢
║ g │ 2.1 ║
╟───┼─────╢
║ h │ 7   ║
╚═══╧═════╝

╔═══╤═════╗
║ a │ 12  ║
╟───┼─────╢
║ g │ 2.1 ║
╚═══╧═════╝
```
{% endtab %}
{% endtabs %}

### **Index by a slice of row**

The **loc** function also accepts string slices of the form \[start: end], e.g **\[\`"a":"e"\`]**. This will return all values from label positions `a` to `e`.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

const data = [12, 34, 2.2, 2, 30, 30, 2.1, 7]
const index = ["a", "b", "c", "d", "e", "f", "g", "h"]
let s = new dfd.Series(data, { index })
s.print()

s.loc([`"a":"e"`]).print()
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
╔═══╤═════╗
║ a │ 12  ║
╟───┼─────╢
║ b │ 34  ║
╟───┼─────╢
║ c │ 2.2 ║
╟───┼─────╢
║ d │ 2   ║
╚═══╧═════╝
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Note that when using loc. We expect you to pass labels in the correct format. That is, string labels must be explicitly quoted. For example, the following loc slice will throw an error:\
`s.loc(["a:e"]).print()`\
For the slice above to work, you must quote each slice, e.g:\
`s.loc(["a":"e"]).print()`\
\
_**Inner quotes are not needed for numeric indices!**_
{% endhint %}

### By specifying a start index in a slice, all values after that index are returned.

{% tabs %}
{% tab title="Node" %}
```javascript
const data = [12, 34, 2.2, 2, 30, 30, 2.1, 7]
let s = new dfd.Series(data)

s.loc([`1:`]).print()
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
╔═══╤═════╗
║ 1 │ 34  ║
╟───┼─────╢
║ 2 │ 2.2 ║
╟───┼─────╢
║ 3 │ 2   ║
╟───┼─────╢
║ 4 │ 30  ║
╟───┼─────╢
║ 5 │ 30  ║
╟───┼─────╢
║ 6 │ 2.1 ║
╟───┼─────╢
║ 7 │ 7   ║
╚═══╧═════╝
```
{% endtab %}
{% endtabs %}

### Slice Series by boolean condition

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


let s = new dfd.Series([12, 34, 2.2, 2, 30, 30, 2.1, 7])
s.loc(s.gt(20)).print()
```
{% endtab %}
{% endtabs %}

```
╔═══╤════╗
║ 1 │ 34 ║
╟───┼────╢
║ 4 │ 30 ║
╟───┼────╢
║ 5 │ 30 ║
╚═══╧════╝
```
