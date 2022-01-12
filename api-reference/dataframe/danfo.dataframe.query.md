---
description: Query the DataFrame by the result of a logical comparison or boolean mask.
---

# DataFrame.query

danfo.DataFrame.**query**(kwargs)

| Parameters | Type   | Description                                                                                                                                                                                                                                                                                                                                  | Default                                                                                        |
| ---------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| kwargs     | Object | <p>{</p><p><strong>condition:</strong> A logical boolean mask,</p><p><strong>column</strong> : str, name of the column</p><p><strong>is:</strong> Logical operator, one of ">", "&#x3C;", ">=", "&#x3C;=", and. "=="</p><p><strong>to</strong>: Int, Float, Str. Value to compare against,</p><p><strong>inplace</strong>: boolean. true</p> | <p>false. Whether to perform operation to the original Object or create a new one.</p><p>}</p> |

## **Examples**

## **Query a DataFrame using a boolean mask**

{% hint style="info" %}
Querying by a boolean condition is supported from v0.3.0 and above.
{% endhint %}

```javascript
const dfd = require("danfojs-node")

let data = {
    "A": ["Ng", "Yu", "Mo", "Ng"],
    "B": [34, 4, 5, 6],
    "C": [20, 20, 30, 40]
}
let df = new dfd.DataFrame(data)
df.print()
let query_df = df.query(df["B"].gt(5))
query_df.print() //after query
```

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ Ng                │ 34                │ 20                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ Yu                │ 4                 │ 20                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ Mo                │ 5                 │ 30                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ Ng                │ 6                 │ 40                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ Ng                │ 34                │ 20                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ Ng                │ 6                 │ 40                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

It also supports condition chaining as long as the final boolean mask is the same length as the DataFrame rows. For example in the following code, we use multiple chaining conditions:

```javascript
const dfd = require("danfojs-node")

let data = {
    "A": ["Ng", "Yu", "Mo", "Ng"],
    "B": [34, 4, 5, 6],
    "C": [20, 20, 30, 40]
}
let df = new dfd.DataFrame(data)
df.print()

let query_df = df.query(df["B"].gt(5).and(df["C"].lt(40)))
query_df.print() //after query
```

```
// output
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ Ng                │ 34                │ 20                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ Yu                │ 4                 │ 20                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ Mo                │ 5                 │ 30                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ Ng                │ 6                 │ 40                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ Ng                │ 34                │ 20                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

## **Query a DataFrame using logical operators**

{% hint style="info" %}
This is only supported in older versions. That is versions lower than v1.0.0
{% endhint %}

To query a DataFrame, you can specify the column to use, the logical operator (">", "<", ">=", "<=", and. "=="), and the value to compare against.

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
```
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

## **Query by a string column in a DataFrame**

{% hint style="info" %}
This is only supported in older versions. That is versions lower than v1.0.0
{% endhint %}

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
```
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
