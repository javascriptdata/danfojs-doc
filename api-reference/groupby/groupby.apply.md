---
description: Apply custom aggregate function to grouped data
---

# Groupby.apply

danfo.Groupby.**apply**\(callable\) \[[source](https://github.com/javascriptdata/danfojs/blob/9bfda6dcb6b2b620591ec7b3340d35e3f801c8ab/src/danfojs-base/aggregators/groupby.ts#L552)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| callable | Function \| function to be applied to grouped data. the callable functons takes in DataFrame as argument adn returns DataFrame or Series | Undefined |  |

**Returns:**

       ****return **DataFrame**

## **Examples**

Using apply to create a custom function that subtract the minimum value of each grouped data from each of its values

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = {
      A: ['foo', 'bar', 'foo', 'bar',

        'foo', 'bar', 'foo', 'foo'],

      B: ['one', 'one', 'two', 'three',

        'two', 'two', 'one', 'three'],

      C: [1, 3, 2, 4, 5, 2, 6, 7],

      D: [3, 2, 4, 1, 5, 6, 7, 8]
    };
  
let df = new dfd.DataFrame(data);
let groupDf = df.groupby(["A", "B"]).col(['C', 'D']);

const subMin = (x) => {
  //find the min across column
  return x.sub(x.min({axis:0}));
};

groupDf.apply(subMin).print();

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
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 │ D                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ foo               │ one               │ 0                 │ 0                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ foo               │ one               │ 5                 │ 4                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ foo               │ two               │ 0                 │ 0                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ foo               │ two               │ 3                 │ 1                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4          │ foo               │ three             │ 0                 │ 0                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 5          │ bar               │ one               │ 0                 │ 0                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 6          │ bar               │ three             │ 0                 │ 0                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 7          │ bar               │ two               │ 0                 │ 0                 ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

\*\*\*\*
