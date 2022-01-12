---
description: Return a cumulative sum of a series
---

# Series.cumSum

> danfo.Series.**cumSum**(options)&#x20;

| Parameters | Type   | Description                                                    | Default                                                |
| ---------- | ------ | -------------------------------------------------------------- | ------------------------------------------------------ |
| options    | Object | **inplace**: Whether to perform the operation in-place or not. | <p>{</p><p><strong>inplace</strong>: false</p><p>}</p> |

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


let data1 = [10, 45, 56, 25, 23, 20, 10]
let sf1 = new dfd.Series(data1)

sf1.cumSum().print()
```
{% endtab %}

{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.jsdelivr.net/npm/danfojs@0.2.4/dist/index.min.js"></script>
    <title>Document</title>
</head>

<body>

    <script>

      //danfo is exposed on dfd namespace 
      s = new dfd.Series([1,2,3,4,5]) 

    </script>

</body>

</html>
```
{% endtab %}
{% endtabs %}

```
╔═══╤═════╗
║ 0 │ 10  ║
╟───┼─────╢
║ 1 │ 55  ║
╟───┼─────╢
║ 2 │ 111 ║
╟───┼─────╢
║ 3 │ 136 ║
╟───┼─────╢
║ 4 │ 159 ║
╟───┼─────╢
║ 5 │ 179 ║
╟───┼─────╢
║ 6 │ 189 ║
╚═══╧═════╝
```
