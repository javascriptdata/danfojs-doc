---
description: Access a single value for a row/column label pair.
---

# Series.at

> danfo.Series.at(label)

| Parameters | Type   | Description       | Default |
| ---------- | ------ | ----------------- | ------- |
| label      | String | label to index by |         |

**Return:** Scalar



{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let sf = new dfd.Series(["Apples", "Mango", "Banana", "Pear"],
    { index: ["a", "b", "c", "d"] }
)

sf.at("a")

// "Apples"
```
{% endtab %}
{% endtabs %}
