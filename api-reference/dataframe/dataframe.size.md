---
description: >-
  Return an int representing the number of elements in this object. Return the
  number of rows if Series. Otherwise return the number of rows times number of
  columns if DataFrame.
---

# DataFrame.size

danfo.DataFrame.**size** \[[source](https://github.com/opensource9ja/danfojs/blob/eb5919d2cac34271fc3b725fa24aa3ad4eacde37/danfojs/src/core/generic.js#L290)\]

**Returns:**

       ****return **Int**

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"A": [-20.1, 30, 47.3, -20],
            "B": [34, -4, 5, 6], 
            "C": [20, -20, 30, -40]}
let df = new dfd.DataFrame(data, {index: ["a", "b", "c", "d"]})

console.log(df.size)


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
12
```
{% endtab %}
{% endtabs %}

