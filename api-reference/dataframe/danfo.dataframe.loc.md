---
description: Access a group of rows and columns by label(s)
---

# DataFrame.loc

danfo.DataFrame.**loc**\(axis\) \[[source](https://github.com/opensource9ja/danfojs/blob/cf5c7ae3a009458e61eedd18d9c9b5b6b10d5276/danfojs/src/core/frame.js#L125)\]

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
        <p><b>rows</b>: Array, labels of row index</p>
        <p><b>columns</b>: Array, labels of column names</p>
        <p>}</p>
      </td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

**Returns:**

       ****return **DataFrame**

## **Examples**

`.loc()` is primarily label based, but row index also accepts numeric slices

Allowed inputs are:

* A single label, e.g. `5` or `'a'`, \(note that `5` is interpreted as a _label_ of the index, and **not** as an integer position along the index\).
* A list or array of labels, e.g. `['a', 'b', 'c']`.
* A slice object with labels, e.g. `'a:f'`.

  _**Note:** both the start and the stop labels are included._

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
```text

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

### **Index by a slice of the row and return all columns**

The **loc** function also accepts string slices of the form \[start: end\], e.g "a: c". This will return all values between the first occurrence of label "a" and the last occurrence of the label "c".

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"],
            "Count": [21, 5, 30, 10],
            "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data)
let sub_df = df.loc({rows: ["a:c"]})
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
║ a │ Apples            │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ b │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ c │ Banana            │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ d │ Pear              │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


 //after slicing 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ a │ Apples            │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ b │ Mango             │ 5                 │ 300               ║
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
```text
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
```text

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

### Indexing row axes by slices

Column axis cannot be indexed by slices. That means something like columns: \["Name: Count"\] will not work. You can, however, slice the row axis, and list the names of columns you want. 

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"],
            "Count": [21, 5, 30, 10],
            "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data, { index: ["a", "b", "c", "d"] })
df.print()
let sub_df = df.loc({ rows: ["b:d"], columns: ["Name", "Price"] })
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
║ b │ Mango             │ 300               ║
╟───┼───────────────────┼───────────────────╢
║ c │ Banana            │ 40                ║
╟───┼───────────────────┼───────────────────╢
║ d │ Pear              │ 250               ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

### More default slicing behaviour

If you specify a slice start position, **loc** automatically returns all values after that position. For instance:

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"],
            "Count": [21, 5, 30, 10],
            "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data, { index: ["a", "b", "c", "d"] })
df.print()
let sub_df = df.loc({ rows: ["b:"], columns: ["Name", "Price"] })
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
║ b │ Mango             │ 300               ║
╟───┼───────────────────┼───────────────────╢
║ c │ Banana            │ 40                ║
╟───┼───────────────────┼───────────────────╢
║ d │ Pear              │ 250               ║
╚═══╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}



