---
description: Access a single value for a row/column label pair.
---

# DataFrame.at

> danfo.DataFrame.at(row, column)

| Parameters | Type           | Description               | Default |
| ---------- | -------------- | ------------------------- | ------- |
| row        | Number, String | row position in the index |         |
| column     | String         | Column position           |         |

**Return:** Scalar



{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    "Name": ["Apples", "Mango", "Banana", "Pear"],
    "Count": [21, 5, 30, 10],
    "Price": [200, 300, 40, 250]
}

let df = new dfd.DataFrame(data, { index: [1, "b", "c", "d"] })
df.at(1, "Count")

//output
21
```
{% endtab %}
{% endtabs %}
