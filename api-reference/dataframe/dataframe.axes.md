---
description: >-
  Return an Object containing the axis of the DataFrame. It has the row axis
  labels and column axis labels as the only members.
---

# DataFrame.axis

danfo.DataFrame.**axis**&#x20;

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {"A": [-20.1, 30, 47.3, -20],
            "B": [34, -4, 5, 6], 
            "C": [20, -20, 30, -40]}
            
let df = new dfd.DataFrame(data, {index: ["a", "b", "c", "d"]})

console.log(df.axis)

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
{ index: [ 'a', 'b', 'c', 'd' ], columns: [ 'A', 'B', 'C' ] }
```
{% endtab %}
{% endtabs %}
