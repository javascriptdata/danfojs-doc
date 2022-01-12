---
description: >-
  Pretty prints default (10) number of rows in a DataFrame or Series to the
  console
---

# DataFrame.print

danfo.DataFrame.**print()**&#x20;

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Abs": [20.2, 30, 47.3] ,
             "Count": [34, 4, 5] ,
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
```
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
```
DataFrame {
  '$dataIncolumnFormat': [ [ 20.2, 30, 47.3 ], [ 34, 4, 5 ], [ 'NG', 'FR', 'GH' ] ],
  '$index': [ 0, 1, 2 ],
  '$columns': [ 'Abs', 'Count', 'country code' ],
  '$dtypes': [ 'float32', 'int32', 'string' ],
  '$isSeries': false,
  '$config': Configs {
    tableDisplayConfig: {},
    tableMaxRow: 10,
    tableMaxColInConsole: 10,
    dtypeTestLim: 20,
    lowMemoryMode: false
  },
  '$data': [ [ 20.2, 34, 'NG' ], [ 30, 4, 'FR' ], [ 47.3, 5, 'GH' ] ]
}

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ Abs               │ Count             │ country code      ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ 20.2              │ 34                │ NG                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ 30                │ 4                 │ FR                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ 47.3              │ 5                 │ GH                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
