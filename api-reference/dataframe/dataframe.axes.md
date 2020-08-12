---
description: >-
  Return an Object containing the axes of the DataFrame. It has the row axis
  labels and column axis labels as the only members. They are returned in that
  order.
---

# DataFrame.axes

danfo.DataFrame.**axes** \[[source](https://github.com/opensource9ja/danfojs/blob/eb5919d2cac34271fc3b725fa24aa3ad4eacde37/danfojs/src/core/generic.js#L290)\]

**Returns:**

       ****return **Object**

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"A": [-20.1, 30, 47.3, -20],
            "B": [34, -4, 5, 6], 
            "C": [20, -20, 30, -40]}
            
let df = new dfd.DataFrame(data, {index: ["a", "b", "c", "d"]})

console.log(df.axes)


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
{ index: [ 'a', 'b', 'c', 'd' ], columns: [ 'A', 'B', 'C' ] }
```
{% endtab %}
{% endtabs %}

