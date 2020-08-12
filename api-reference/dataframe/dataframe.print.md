---
description: Pretty prints n number of rows in a DataFrame or Series to the console
---

# DataFrame.print

danfo.DataFrame.**print\(**rows**\)** \[[source](https://github.com/opensource9ja/danfojs/blob/eb5919d2cac34271fc3b725fa24aa3ad4eacde37/danfojs/src/core/generic.js#L290)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| **rows** | Int | Number of rows to display. | 5 |

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Abs": [20.2, 30, 47.3] ,
             "Count": [34, 4, 5, 6] ,
             "country code": ["NG", "FR", "GH"] }


let df = new dfd.DataFrame(data)
df.print()
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

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Abs               │ Count             │ country code      ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 20.2              │ 34                │ NG                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 30                │ 4                 │ FR                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 47.3              │ 5                 │ GH                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

Using JavaScript default **console.log** to display a DataFrame will return the Object instead unless you manually cast it to a String

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Abs": [20.2, 30, 47.3] ,
             "Count": [34, 4, 5, 6] ,
             "country code": ["NG", "FR", "GH"] }


let df = new dfd.DataFrame(data)
console.log(df)
console.log(String(df));
// console.log(df + ""); //same result as above
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
DataFrame {
  kwargs: { columns: [ 'Abs', 'Count', 'country code' ] },
  series: false,
  data: [ [ 20.2, 34, 'NG' ], [ 30, 4, 'FR' ], [ 47.3, 5, 'GH' ] ],
  row_data_tensor: Tensor {
    kept: false,
    isDisposedInternal: false,
    shape: [ 3, 3 ],
    dtype: 'float32',
    size: 9,
    strides: [ 3 ],
    dataId: {},
    id: 0,
    rankType: '2'
  },
  index_arr: [ 0, 1, 2 ],
  columns: [ 'Abs', 'Count', 'country code' ],
  col_data: [ [ 20.2, 30, 47.3 ], [ 34, 4, 5 ], [ 'NG', 'FR', 'GH' ] ],
  col_data_tensor: Tensor {
    kept: false,
    isDisposedInternal: false,
    shape: [ 3, 3 ],
    dtype: 'float32',
    size: 9,
    strides: [ 3 ],
    dataId: {},
    id: 1,
    rankType: '2'
  },
  col_types: [ 'float32', 'int32', 'string' ],
  Abs: [Getter/Setter],
  Count: [Getter/Setter],
  'country code': [Getter/Setter]
}

 //after casting to string

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Abs               │ Count             │ country code      ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 20.2              │ 34                │ NG                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 30                │ 4                 │ FR                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 47.3              │ 5                 │ GH                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

