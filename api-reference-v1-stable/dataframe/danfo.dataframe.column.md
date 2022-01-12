---
description: Return the elements of the specified column in the DataFrame
---

# DataFrame.column

danfo.DataFrame.**column**(column) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L1217)]

| Parameters | Type   | Description                           | Default |
| ---------- | ------ | ------------------------------------- | ------- |
| column     | String | The name of a column in the DataFrame |         |

**Returns:**

&#x20;      ****       return **Series**

## **Examples**

## **Select a single column from a DataFrame**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
let data = { "Name": ["Apples", "App", "Banana", undefined],
            "Count": [NaN, 5, NaN, 10] ,
            "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data)

df.column("Name").print()

//Alternatively, you can retrieve columns by using the object property
df['Name'].print() //produces the same result as above

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
╔═══╤═══════════╗
║ 0 │ Apples    ║
╟───┼───────────╢
║ 1 │ App       ║
╟───┼───────────╢
║ 2 │ Banana    ║
╟───┼───────────╢
║ 3 │ undefined ║
╚═══╧═══════════╝

╔═══╤═══════════╗
║ 0 │ Apples    ║
╟───┼───────────╢
║ 1 │ App       ║
╟───┼───────────╢
║ 2 │ Banana    ║
╟───┼───────────╢
║ 3 │ undefined ║
╚═══╧═══════════╝

```
{% endtab %}
{% endtabs %}

To select more than one column with specific rows, you can use any of the following: [DataFrame.loc](danfo.dataframe.loc.md), [DataFrame.iloc](danfo.dataframe.iloc.md) or [DataFrame.query](danfo.dataframe.query.md)
