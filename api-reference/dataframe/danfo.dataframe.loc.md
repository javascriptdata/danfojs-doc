---
description: Access a group of rows and columns by label(s)
---

# DataFrame.loc

danfo.DataFrame.**loc**(args)

| Parameters | Type   | Description                                                                                                                                          | Default |
| ---------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- | ------- |
| args       | Object | <p>{</p><p><strong>rows</strong>: Array, labels, Boolean mask of row index</p><p><strong>columns</strong>: Array, labels of column names</p><p>}</p> |         |

## **Examples**

`.loc()` is label position based-from `0` to `length-1` of the row axis.

Allowed inputs for are:

* An integer, e.g. `"r1"`.
* A list or array of integers, e.g. `["a", "b", "d"]`.
* A boolean mask. E.g \[ true, false, false ]
* A string slice object with ints, e.g. `[`'`"a":"d"'], ["1:4"]`

_**Note:** only \*\*\*\* the start label is included, and the end label is ignored._

`.loc` will raise a `ValueEror` if a requested label is not found.

### **Index by specific rows and return all columns**

If the row's index is specified and the columns are not, then it returns all columns and just the specified rows.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"],
            "Count": [21, 5, 30, 10],
            "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data, {index: ["a", "b", "c", "d"]})
df.print()
let sub_df = df.loc({rows: ["a", "c"]})
sub_df.print()
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
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ a │ Apples            │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ b │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ c │ Banana            │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ d │ Pear              │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


 Shape: (2,3) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ a │ Apples            │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ c │ Banana            │ 30                │ 40                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### **Index by a list of column names and return all rows**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"],
            "Count": [21, 5, 30, 10],
            "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data, {index: ["a", "b", "c", "d"]})
df.print()
let sub_df = df.loc({columns: ["Count", "Price"]})
sub_df.print()
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
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ a │ Apples            │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ b │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ c │ Banana            │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ d │ Pear              │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


 //after indexing

╔═══╤═══════════════════╤═══════════════════╗
║   │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────╢
║ a │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────╢
║ b │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────╢
║ c │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────╢
║ d │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Index both axes by the specified labels

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"],
            "Count": [21, 5, 30, 10],
            "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data, { index: ["a", "b", "c", "d"] })
df.print()
let sub_df = df.loc({ rows: ["c","d"], columns: ["Name", "Price"] })
sub_df.print()
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
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ a │ Apples            │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ b │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ c │ Banana            │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ d │ Pear              │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


//after slicing

╔═══╤═══════════════════╤═══════════════════╗
║   │ Name              │ Price             ║
╟───┼───────────────────┼───────────────────╢
║ c │ Banana            │ 40                ║
╟───┼───────────────────┼───────────────────╢
║ d │ Pear              │ 250               ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

## **Index by a slice of row**

The **loc** function also accepts string slices of the form \[start: end], e.g **\[\`"a":"c"\`]**. This will return all values from label positions `a` to c.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"],
            "Count": [21, 5, 30, 10],
            "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data, { index: ["a", "b", "c", "d"] })
df.print()
let sub_df = df.loc({ rows: [`"a":"c"`], columns: ["Name", "Price"] })
sub_df.print()
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
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ Name              │ Count             │ Price             ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ a          │ Apples            │ 21                │ 200               ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ b          │ Mango             │ 5                 │ 300               ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ c          │ Banana            │ 30                │ 40                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ d          │ Pear              │ 10                │ 250               ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

╔════════════╤═══════════════════╤═══════════════════╗
║            │ Name              │ Price             ║
╟────────────┼───────────────────┼───────────────────╢
║ a          │ Apples            │ 200               ║
╟────────────┼───────────────────┼───────────────────╢
║ b          │ Mango             │ 300               ║
╚════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Note that when using loc with alphabetic slices. We expect you to pass labels in the correct format. That is, string labels must be explicitly quoted. For example, the following loc slice will throw an error:\
df`.loc({ row: ["a:e"]}).print()`\
For the slice above to work, you must quote each slice, e.g:\
df``.loc({ row: [`"a":"e"`]}).print()``\
\
_**Inner**_ _**quotes are not needed for numeric indices!**_
{% endhint %}

### Slice DataFrame rows by boolean condition

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    "Name": ["Apples", "Mango", "Banana", "Pear"],
    "Count": [21, 5, 30, 10],
    "Price": [200, 300, 40, 250]
}

let df = new dfd.DataFrame(data, { index: ["a", "b", "c", "d"] })
let sub_df = df.loc({ rows: df["Count"].gt(6) })
sub_df.print()
```
{% endtab %}
{% endtabs %}

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ Name              │ Count             │ Price             ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ a          │ Apples            │ 21                │ 200               ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ c          │ Banana            │ 30                │ 40                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ d          │ Pear              │ 10                │ 250               ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

```

### Slice DataFrame rows by multiple boolean conditions

{% hint style="info" %}
_By design, you can chain as many boolean logic as required, as long as they resolve to a Boolean array of the same length as the DataFrame._
{% endhint %}

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    "Name": ["Apples", "Mango", "Banana", "Pear"],
    "Count": [21, 5, 30, 10],
    "Price": [200, 300, 40, 250]
}

let df = new dfd.DataFrame(data, { index: ["a", "b", "c", "d"] })
let condition = df["Count"].gt(6).and(df["Price"].lt(250))
let sub_df = df.loc({ rows: condition })
sub_df.print()
```
{% endtab %}
{% endtabs %}

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ Name              │ Count             │ Price             ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ a          │ Apples            │ 21                │ 200               ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ c          │ Banana            │ 30                │ 40                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

### Slice DataFrame with boolean mask

{% hint style="info" %}
_You can index a DataFrame with an array of boolean values as long as they resolve to an array of the same length as the DataFrame._
{% endhint %}

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    "Name": ["Apples", "Mango", "Banana", "Pear"],
    "Count": [21, 5, 30, 10],
    "Price": [200, 300, 40, 250]
}

let df = new dfd.DataFrame(data, { index: ["a", "b", "c", "d"] })

let sub_df = df.loc({ rows: [false, true, true, true] })
sub_df.print()
```
{% endtab %}
{% endtabs %}

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ Name              │ Count             │ Price             ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ b          │ Mango             │ 5                 │ 300               ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ c          │ Banana            │ 30                │ 40                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ d          │ Pear              │ 10                │ 250               ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

```
