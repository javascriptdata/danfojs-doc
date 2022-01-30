---
description: Access a single value for a row/column pair by integer position.
---

# Series.iat

> danfo.Series.iat(index)

| Parameters | Type   | Description  | Default |
| ---------- | ------ | ------------ | ------- |
| index      | Number | index value  |         |

**Return:** Scalar



{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let sf = new dfd.Series(["Apples", "Mango", "Banana", "Pear"],
    { index: ["a", "b", "c", "d"] }
)

sf.iat(1)

// "Mango"
```
{% endtab %}
{% endtabs %}
