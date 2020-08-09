---
description: Purely integer-location based indexing for selection by position.
---

# DataFrame.iloc

danfo.DataFrame.**iloc**\(axis\) \[[source](https://github.com/opensource9ja/danfojs/blob/fe56860b0a303d218d60ba71dee6abf594401556/danfojs/src/core/frame.js#L254)\]

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameters</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Default</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">kwargs</td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">
        <p>{</p>
        <p><b>rows</b>: Array, index of row position</p>
        <p><b>columns</b>: Array, index of position along columns</p>
        <p>}</p>
      </td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

**Returns:**

       ****return **DataFrame**

## **Examples**

`.iloc()` is primarily integer position based \(from `0` to `length-1` of the axis\).

Allowed inputs are:

* An integer, e.g. `5`.
* A list or array of integers, e.g. `[4, 3, 0]`.
* A string slice object with ints, e.g. `"1:7"`

_**Note:** both the start and the stop labels are included._

`.iloc` will raise`IndexError` if a requested indexer is out-of-bounds.

### **Indexing specific rows by index and return all columns**

If the row's index is specified and the columns are not, then it returns all columns and just the specified rows.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [{ "Name": ["Apples", "Mango", "Banana", "Pear"] },
           { "Count": [21, 5, 30, 10] },
           { "Price": [200, 300, 40, 250] }]

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
```text
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

The [**iloc**](danfo.dataframe.iloc.md) function also accepts string slices of the form \[start: end\], e.g "\[1: 4\]". This will return all values between index position 1 and 4 inclusively. 

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [{ "Name": ["Apples", "Mango", "Banana", "Pear"] },
           { "Count": [21, 5, 30, 10] },
           { "Price": [200, 300, 40, 250] }]

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
```text
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ Banana            │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ Pear              │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### **Index by a slice of column and return all rows**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [{ "Name": ["Apples", "Mango", "Banana", "Pear"] },
           { "Count": [21, 5, 30, 10] },
           { "Price": [200, 300, 40, 250] }]

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
```text
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
const dfd = require("danfojs")

let data = [{ "Name": ["Apples", "Mango", "Banana", "Pear"] },
           { "Count": [21, 5, 30, 10] },
           { "Price": [200, 300, 40, 250] }]

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
```text

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


 //after slice

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
const dfd = require("danfojs")

let data = [{ "Name": ["Apples", "Mango", "Banana", "Pear"] },
           { "Count": [21, 5, 30, 10] },
           { "Price": [200, 300, 40, 250] }]

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
```text
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


 //after slice

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

### More default slicing behaviour

If you specify a slice start position, **iloc** automatically returns all values after that position. For instance:

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [{ "Name": ["Apples", "Mango", "Banana", "Pear"] },
           { "Count": [21, 5, 30, 10] },
           { "Price": [200, 300, 40, 250] }]

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
```text
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


 //After slicing

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



