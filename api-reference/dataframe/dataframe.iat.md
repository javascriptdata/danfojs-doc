---
description: Access a single value for a row/column pair by integer position.
---

# DataFrame.iat

> danfo.DataFrame.iat(row, column)

| Parameters | Type   | Description           | Default |
| ---------- | ------ | --------------------- | ------- |
| row        | Number | row index position    |         |
| column     | Number | Column index position |         |

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
df.iat(1, 2)

//output
300
```
{% endtab %}
{% endtabs %}
