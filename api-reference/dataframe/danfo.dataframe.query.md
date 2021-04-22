---
description: >-
  Query the DataFrame by the result of a logical comparison. Supports logical
  operations like (">", "<", ">=", "<=", "==" and "!=")
---

# DataFrame.query

danfo.DataFrame.**query**\(kwargs\) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L1011)\]

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
        <p>{<b>column</b> : str, name of the column</p>
        <p><b> is: </b>Logical operator, one of &quot;&gt;&quot;, &quot;&lt;&quot;,
          &quot;&gt;=&quot;, &quot;&lt;=&quot;, &quot;==&quot; and &quot;!=&quot;</p>
        <p><b>to</b>: Int, Float, Str. Value to compare against,</p>
        <p><b>inplace</b>: boolean. true | false. Whether to perform operation to
          the original Object or create a new one.</p>
        <p>}</p>
      </td>
      <td style="text-align:left">{<b>inplace</b>: false}</td>
    </tr>
  </tbody>
</table>

**Returns:**

       ****return **new DataFrame**

## **Examples**

## **Query a DataFrame using logical operators**

To query a DataFrame, you can specify the column to use, the logical operator \("&gt;", "&lt;", "&gt;=", "&lt;=", "==" and "!="\), and the value to compare against. 

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"A": [30, 1, 2, 3],
           "B": [34, 4, 5, 6],
           "C": [20, 20, 30, 40]}
           
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })
df.print() //before query

let query_df = df.query({ "column": "B", "is": ">", "to": 5 })
query_df.print() //after query
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
//before query
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 1                 │ 2                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 4                 │ 5                 │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 20                │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 39                │ 89                │ 78                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝

//after query
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 20                │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 39                │ 89                │ 78                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
let data = {"A": [30, 1, 2, 3],
           "B": [34, 4, 5, 6],
           "C": [20, 20, 30, 40]}
           
let df = new dfd.DataFrame(data)

df.print()

let query_df = df.query({ "column": "A", "is": ">", "to": 9 })
query_df.print() //after query

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
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 30                │ 34                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 4                 │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 5                 │ 30                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 3                 │ 6                 │ 40                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝

//after query

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 30                │ 34                │ 20                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

## **Query by a string column in a DataFrame**

The query method also works on string columns. 

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
let data = {"A": ["Ng", "Yu", "Mo", "Ng"],
            "B": [34, 4, 5, 6], 
            "C": [20, 20, 30, 40]}
            
let df = new dfd.DataFrame(data)

df.print()

let query_df = df.query({ column: "A", is: "==", to: "Ng"})
query_df.print() //after query

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
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ Ng                │ 34                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Yu                │ 4                 │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ Mo                │ 5                 │ 30                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ Ng                │ 6                 │ 40                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝

//after query

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ Ng                │ 34                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ Ng                │ 6                 │ 40                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

## **Query a DataFrame inplace**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"A": [30, 1, 2, 3],
           "B": [34, 4, 5, 6],
           "C": [20, 20, 30, 40]}
           
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

df.query({
    column: "B",
    is: ">",
    to: 5,
    inplace: true
})
df.print()

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
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 30                │ 34                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 3                 │ 6                 │ 40                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

