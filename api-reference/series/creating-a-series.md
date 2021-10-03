# Creating a Series

In order to create a Series, you need to call the new Keyword and pass a flat data structure. In the following examples, we show you how to create a Series by specifying different config options. 

### Creating a Series from an object:

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

obj_data = { 'B': ["bval1", "bval2", "bval3", "bval4"] }
df = new dfd.Series(obj_data)
df.print()
```
{% endtab %}

{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <!--danfojs CDN -->
<script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.0/lib/bundle.min.js"></script>    <title>Document</title>
</head>

<body>

    <script>

         json_data = [{ A: 0.4612, B: 4.28283, C: -1.509, D: -1.1352 },
            { A: 0.5112, B: -0.22863, C: -3.39059, D: 1.1632 },
            { A: 0.6911, B: -0.82863, C: -1.5059, D: 2.1352 },
            { A: 0.4692, B: -1.28863, C: 4.5059, D: 4.1632 }]

        df = new dfd.DataFrame(json_data)
        df.print()

    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

```javascript
╔═══╤═══════╗
║ 0 │ bval1 ║
╟───┼───────╢
║ 1 │ bval2 ║
╟───┼───────╢
║ 2 │ bval3 ║
╟───┼───────╢
║ 3 │ bval4 ║
╚═══╧═══════╝
```

### Creating a Series from an array

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

obj_data = ["bval1", "bval2", "bval3", "bval4"]
df = new dfd.Series(obj_data)
df.print()
```
{% endtab %}

{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <!--danfojs CDN -->
<script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.0/lib/bundle.min.js"></script>    <title>Document</title>
</head>

<body>

    <script>

         json_data = [{ A: 0.4612, B: 4.28283, C: -1.509, D: -1.1352 },
            { A: 0.5112, B: -0.22863, C: -3.39059, D: 1.1632 },
            { A: 0.6911, B: -0.82863, C: -1.5059, D: 2.1352 },
            { A: 0.4692, B: -1.28863, C: 4.5059, D: 4.1632 }]

        df = new dfd.DataFrame(json_data)
        df.print()

    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

```text
╔═══╤═══════╗
║ 0 │ bval1 ║
╟───┼───────╢
║ 1 │ bval2 ║
╟───┼───────╢
║ 2 │ bval3 ║
╟───┼───────╢
║ 3 │ bval4 ║
╚═══╧═══════╝
```

### Creating a Series and specifying index and dtypes

You can create a Series and specify options like index, dtypes, as well as configuration options for display, and memory mode etc. 

> Note: Specifing dtypes, and index on Series creation makes the process slightly faster.

{% tabs %}
{% tab title="Node" %}
```javascript
import { Series } from "danfojs"

let data1 = [1, 2, 3, 4, 5];
let index = ["a", "b", "c", "d", "e"];
let dtypes = ["int32",]

let df = new Series(data1, { index, dtypes });
df.print()
```
{% endtab %}
{% endtabs %}

```text
╔═══╤═══╗
║ a │ 1 ║
╟───┼───╢
║ b │ 2 ║
╟───┼───╢
║ c │ 3 ║
╟───┼───╢
║ d │ 4 ║
╟───┼───╢
║ e │ 5 ║
╚═══╧═══╝
```

### Creating a Series and specifying memory mode

To use less space on Series creation, you can set the low memory mode as demonstrated below:

```javascript
import { Series } from "danfojs"

let data1 = [1, 2.3, 3, 4, 5, "girl"];

let df = new Series(data1, {
    config: { lowMemoryMode: true }
});
df.print()
```

{% hint style="info" %}
**Note**: In low memory mode, less space is used by the Series.
{% endhint %}

