# Series.iloc

danfo.Series.**iloc**()&#x20;

| Parameters | Type                  | Description                                                            | Default |
| ---------- | --------------------- | ---------------------------------------------------------------------- | ------- |
| rows       | Array or String slice | Array, string slice, index of row positions boolean mask to filter by. |         |

## **Examples**

`.iloc()` is primarily integer position based (from `0` to `length-1` of the axis).

Allowed inputs are:

* An integer, e.g. `5`.
* A list or array of integers, e.g. `[4, 3, 0]`.
* A boolean mask. E.g \[ true, false, false ]
* A string slice object with ints, e.g. `"1:7"`

_**Note:** only \*\*\*\* the start label is included, and the end label is ignored._

`.iloc` will raise`IndexError` if a requested indexer is out-of-bounds.

### **Indexing specific rows by index**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let s = new dfd.Series([12, 34, 2.2, 2, 30, 30, 2.1, 7])
s.iloc([0,5]).print()
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
║ 0 │ 12 ║
╟───┼────╢
║ 5 │ 30 ║
╚═══╧════╝
```
{% endtab %}
{% endtabs %}

### **Index by a slice of row**

The [**iloc**](../dataframe/danfo.dataframe.iloc.md) function also accepts string slices of the form \[start: end], e.g "\[0: 5]". This will return all values from index positions 0 to 4.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let s = new dfd.Series([12, 34, 2.2, 2, 30, 30, 2.1, 7])
s.iloc(["0:5"]).print()
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
║ 0 │ 12  ║
╟───┼─────╢
║ 1 │ 34  ║
╟───┼─────╢
║ 2 │ 2.2 ║
╟───┼─────╢
║ 3 │ 2   ║
╟───┼─────╢
║ 4 │ 30  ║
╚═══╧═════╝
```
{% endtab %}
{% endtabs %}

By specifying a start index in a slice, all values after that index are returned.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let s = new dfd.Series([12, 34, 2.2, 2, 30, 30, 2.1, 7])
s.iloc(["5:"]).print()
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
s.iloc(s.gt(20)).print()

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
