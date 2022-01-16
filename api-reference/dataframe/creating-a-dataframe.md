---
description: Creates a DataFrame object from flat structure
---

# Creating a DataFrame

danfo.**DataFrame**(data, options)

| Parameters | Type                              | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ---------- | --------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| data       | 2D Array, 2D Tensor, JSON object. | Flat data structure to load into DataFrame                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| options    | Object                            | <p>Optional configuration object. Supported properties are:<br></p><p><strong>index:</strong> Array of numeric or string names for subseting array. If not specified, indexes are auto-generated.<br></p><p><strong>columns:</strong> Array of column names. If not specified, column names are auto generated.<br></p><p><strong>dtypes:</strong> Array of data types for each the column. If not specified, dtypes are/is inferred.<br></p><p><strong>config</strong>: General configuration object for extending or setting NDframe behavior. See full options here</p> |

In order to create a DataFrame, you new to call the new Keyword and pass in a flat data structure. In the following examples, we show you how to create DataFrames by specifying different config options.

### Creating a `DataFrame` from a JSON object:

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


json_data = [{ A: 0.4612, B: 4.28283, C: -1.509, D: -1.1352 },
            { A: 0.5112, B: -0.22863, C: -3.39059, D: 1.1632 },
            { A: 0.6911, B: -0.82863, C: -1.5059, D: 2.1352 },
            { A: 0.4692, B: -1.28863, C: 4.5059, D: 4.1632 }]

df = new dfd.DataFrame(json_data)
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
<script src="https://cdn.jsdelivr.net/npm/danfojs@1.0.1/lib/bundle.js"></script>    <title>Document</title>
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

### Creating a `DataFrame` from an array of array

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let arr = [[12, 34, 2.2, 2], [30, 30, 2.1, 7]]
let df = new dfd.DataFrame(arr, {columns: ["A", "B", "C", "D"]})
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
<script src="https://cdn.jsdelivr.net/npm/danfojs@1.0.1/lib/bundle.js"></script>    <title>Document</title>
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

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 │ D                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ 12                │ 34                │ 2.2               │ 2                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ 30                │ 30                │ 2.1               │ 7                 ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

### Creating a `DataFrame` from a 2D tensor

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
const tf = dfd.tensorflow

let tensor_arr = tf.tensor2d([[12, 34, 2.2, 2], [30, 30, 2.1, 7]])
let df = new dfd.DataFrame(tensor_arr, {columns: ["A", "B", "C", "D"]})
df.print()
df.ctypes.print()
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
<script src="https://cdn.jsdelivr.net/npm/danfojs@1.0.1/lib/bundle.js"></script>    <title>Document</title>
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

```
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 12                │ 34                │ 2.20000004768...  │ 2                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 30                │ 30                │ 2.09999990463...  │ 7                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ A │ int32                ║
╟───┼──────────────────────╢
║ B │ int32                ║
╟───┼──────────────────────╢
║ C │ float32              ║
╟───┼──────────────────────╢
║ D │ int32                ║
╚═══╧══════════════════════╝
```

### Creating a `DataFrame` from an object

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


dates = new dfd.dateRange({ start: '2017-01-01', end: "2020-01-01", period: 4, freq: "Y" })

console.log(dates);

obj_data = {'A': dates,
            'B': ["bval1", "bval2", "bval3", "bval4"],
            'C': [10, 20, 30, 40],
            'D': [1.2, 3.45, 60.1, 45],
            'E': ["test", "train", "test", "train"]
            }

df = new dfd.DataFrame(obj_data)
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
<script src="https://cdn.jsdelivr.net/npm/danfojs@1.0.1/lib/bundle.js"></script>    <title>Document</title>
</head>

<body>

    <script>

        dates = new dfd.date_range({ start: '2017-01-01', end: "2020-01-01", period: 4, freq: "Y" })

        console.log(dates);

        obj_data = {'A': dates,
                    'B': ["bval1", "bval2", "bval3", "bval4"],
                    'C': [10, 20, 30, 40],
                    'D': [1.2, 3.45, 60.1, 45],
                    'E': ["test", "train", "test", "train"]
                    }

        df = new dfd.DataFrame(obj_data)
        df.print()

    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

```
//output in console
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 │ D                 │ E                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 1/1/2017, 1:0...  │ bval1             │ 10                │ 1.2               │ test              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1/1/2018, 1:0...  │ bval2             │ 20                │ 3.45              │ train             ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 1/1/2019, 1:0...  │ bval3             │ 30                │ 60.1              │ test              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 1/1/2020, 1:0...  │ bval4             │ 40                │ 45                │ train             ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

### Creating a `DataFrame` and specifying index, dtypes, columns

You can create a DataFrame and specify options like index, column names, dtypes as well as configuration options like display, memory mode etc.

> Note: Specifing dtypes, column names and index on DataFrame creation makes the process slightly faster.

{% tabs %}
{% tab title="Node" %}
```javascript
import { DataFrame } from "danfojs"

let data1 = [[1, 2.3, 3, 4, 5, "girl"], [30, 40.1, 39, 89, 78, "boy"]];
let index = ["a", "b"];
let columns = ["col1", "col2", "col3", "col4", "col5", "col6"]
let dtypes = ["int32", "float32", "int32", "int32", "int32", "string"]

let df = new DataFrame(data1, { index, columns, dtypes });
df.print()
```
{% endtab %}
{% endtabs %}

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ col1              │ col2              │ col3              │ col4              │ col5              │ col6              ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ a          │ 1                 │ 2.3               │ 3                 │ 4                 │ 5                 │ girl              ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ b          │ 30                │ 40.1              │ 39                │ 89                │ 78                │ boy               ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

### Creating a `DataFrame` and specifying memory mode

To use less space on DataFrame creation, you can set the low memory mode as demonstrated below:

```javascript
import { DataFrame } from "danfojs"

let data1 = [[1, 2.3, 3, 4, 5, "girl"], [30, 40.1, 39, 89, 78, "boy"]];

let df = new DataFrame(data1, {
    config: { lowMemoryMode: true }
});
df.print()
```

{% hint style="info" %}
**Note**: In low memory mode, less space is used by the DataFrame. The drawback is that some operations especially the ones involving column data become slightly slower.
{% endhint %}

For loading flat files like CSV, EXCEL and, JSON into DataFrames, see this [page](../input-output/)
