---
description: >-
  Count non-NaN cells for each column or row. The values NaN and undefined are
  considered NaN
---

# DataFrame.count

danfo.DataFrame.**count**(options)

| Parameters | Type   | Description                                                                         | Default     |
| ---------- | ------ | ----------------------------------------------------------------------------------- | ----------- |
| options    | Object | **axis:** 0 or 1. If 0, compute the mean column-wise, if 1, row-wise. Defaults to 1 | { axis: 1 } |

## **Examples**

## Count Non-NaN values along default axis 1 (column)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", undefined],
           "Count": [NaN, 5, NaN, 10],
           "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data)
df.count().print()
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
╔═══╤═══╗
║ 0 │ 2 ║
╟───┼───╢
║ 1 │ 3 ║
╟───┼───╢
║ 2 │ 2 ║
╟───┼───╢
║ 3 │ 2 ║
╚═══╧═══╝
```
{% endtab %}
{% endtabs %}

## Count Non-NaN values along row axis (0)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", undefined],
           "Count": [NaN, 5, NaN, 10],
           "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data)
df.count({axis: 0}).print()
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
╔═══════╤═══╗
║ Name  │ 3 ║
╟───────┼───╢
║ Count │ 2 ║
╟───────┼───╢
║ Price │ 4 ║
╚═══════╧═══╝
```
{% endtab %}
{% endtabs %}

##
