---
description: Purely integer-location based indexing for selection by position.
---

# DataFrame.iloc

danfo.DataFrame.**iloc**(args) \[[source](https://github.com/opensource9ja/danfojs/blob/fe56860b0a303d218d60ba71dee6abf594401556/danfojs/src/core/frame.js#L254)]

| Parameters | Type   | Description                                                                                                                                         | Default |
| ---------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------- | ------- |
| args       | Object | <p>{</p><p><strong>rows</strong>:  Array, index of row position</p><p><strong>columns</strong>:  Array, index of position along columns</p><p>}</p> |         |

**Returns:**

&#x20;      ****       return **DataFrame**

## **Examples**

`.iloc()` is primarily integer position based (from `0` to `length-1` of the axis).

Allowed inputs are:

* An integer, e.g. `5`.
* A list or array of integers, e.g. `[4, 3, 0]`.
* A string slice object with ints, e.g. `"1:7"`
* A boolean array.

_**Note:** only the start index is included._

`.iloc` will raise`IndexError` if a requested indexer is out-of-bounds.

### **Indexing specific rows by index and return all columns**

If the row's index is specified and the columns are not, then it returns all columns and just the specified rows.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"],
            "Count": [21, 5, 30, 10],
            "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data)
let sub_df = df.iloc({rows: [0,1,3]})
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
║ 0 │ Apples            │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ Pear              │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### **Index by a slice of row and return all columns**

The [**iloc**](danfo.dataframe.iloc.md) function also accepts string slices of the form \[start: end], e.g "\[1: 3]". This will return all values between index position 1 and 3.  The end index is not included.&#x20;

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"],
            "Count": [21, 5, 30, 10],
            "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data)
let sub_df = df.iloc({rows: ["1:3"]})
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
║ 1 │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ Banana            │ 30                │ 40                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### **Index by a slice of column and return all rows**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"],
            "Count": [21, 5, 30, 10],
            "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data)
df.print()

let sub_df = df.iloc({columns: ["1:"]})
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
║ 0 │ Apples            │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ Banana            │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ Pear              │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


 Shape: (4,2) 

╔═══╤═══════════════════╤═══════════════════╗
║   │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Indexing both axes by the specified index

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"],
            "Count": [21, 5, 30, 10],
            "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data)
let sub_df = df.iloc({rows: [0,3], columns: [1,2]})
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
║ 0 │ Apples            │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ Banana            │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ Pear              │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


 //after indexing

╔═══╤═══════════════════╤═══════════════════╗
║   │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### Indexing both axes by slices

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"],
            "Count": [21, 5, 30, 10],
            "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data)
df.print()

let sub_df = df.iloc({rows: ["2:3"], columns: ["1:2"]})
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
║ 0 │ Apples            │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ Banana            │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ Pear              │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


╔═══╤═══════════════════╗
║   │ Count             ║
╟───┼───────────────────╢
║ 2 │ 30                ║
╚═══╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### More default slicing behavior

If you specify a slice start position, **iloc** automatically returns all values after that position. For instance:

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"],
            "Count": [21, 5, 30, 10],
            "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data)
df.print()

let sub_df = df.iloc({rows: ["2:"], columns: ["1:"]})
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
║ 0 │ Apples            │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ Banana            │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ Pear              │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


 Shape: (2,2) 

╔═══╤═══════════════════╤═══════════════════╗
║   │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

