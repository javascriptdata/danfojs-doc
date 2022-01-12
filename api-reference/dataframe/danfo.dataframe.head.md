---
description: Returns the first n rows of the DataFrame based on position.
---

# DataFrame.head

danfo.DataFrame.**head**(rows)&#x20;

| Parameters | Type | Description                  | Default |
| ---------- | ---- | ---------------------------- | ------- |
| rows       | Int  | The number of rows to return | 5       |

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"],
            "Count": [21, 5, 30, 10],
            "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data)
let s_df = df.head(2)
s_df.print()
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
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ Apples            │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Mango             │ 5                 │ 300               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
