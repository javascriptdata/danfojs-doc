---
description: Pretty prints n number of rows in a browser div
---

# DataFrame.to\_table

danfo.DataFrame.**to\_table**\(div\_name, rows\) \[[source](https://github.com/opensource9ja/danfojs/blob/cf5c7ae3a009458e61eedd18d9c9b5b6b10d5276/danfojs/src/core/frame.js#L125)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| **div\_name** | String | Id name of div tag. |  |
| **rows** | Int | Number of rows to display. | 5 |

## **Examples**

### **Setting index to a column in the DataFrame**

{% tabs %}
{% tab title="Browser" %}
```javascript

const dfd = require("danfojs")

let data = [{ "A": [-20, 30, 47.3] },
            { "B": [34, -4, 5, 6] },
            { "C": [20, 20, 30, 30] }]


let df = new dfd.DataFrame(data, {index: ["a", "b", "a"]})
df.print()

df.set_index({key: "A", inplace: true})
df.print()

```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
To print in the console use [DataFrame.print](dataframe.print.md)
{% endhint %}

