---
description: >-
  Installation guides for Node and Browser based environments, including a quick
  10 minute walk through of danfo.js
---

# Getting Started

## Installation

There are three ways to install and use Danfo.js in your application

For Nodejs applications, you can install the [danfojs-node](https://www.npmjs.com/package/danfojs-node) version via package managers like yarn and npm:

```
npm install danfojs-node

or

yarn add danfojs-node
```

For client-side applications built with frameworks like React, Vue, Next.js, etc, you can install the [danfojs](https://www.npmjs.com/package/danfojs) version:

```
npm install danfojs

or

yarn add danfojs
```

For use directly in HTML files, you can add the latest script tag from [JsDelivr](https://www.jsdelivr.com/package/npm/danfojs?version=0.3.1\&path=lib):

```markup
<script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>
```

{% hint style="info" %}
To play with Danfo.js in a Notebook-like environment, see [Dnotebooks](https://dnotebook.jsdata.org/getting-started) [here](https://playnotebook.jsdata.org/demo)
{% endhint %}

## 10 minutes to danfo.js

This is a short introduction to Danfo.js, and its flow is adapted from the official [10 minutes to Pandas](https://pandas.pydata.org/pandas-docs/stable/user_guide/10min.html#min)

We will show you how to use danfo.js in both browser environments and Node.js environments. Most functions except [plotting](https://jsdata.gitbook.io/danfojs/api-reference/plotting) which require a DOM work the same way in both environments.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
```
{% endtab %}

{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>
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

### Creating a DataFrame/Series

You can create a [`Series`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.html#pandas.Series) by passing a list of values, letting Danfo.js create a default integer index:

{% tabs %}
{% tab title="Node" %}
```javascript
s = new dfd.Series([1, 3, 5, undefined, 6, 8])
s.print()
```
{% endtab %}

{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
<script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>    <title>Document</title>
</head>

<body>

    <script>

        s = new dfd.Series([1, 3, 5, undefined, 6, 8])
        s.print()

    </script>

</body>

</html>
```
{% endtab %}
{% endtabs %}

```
//output
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 1                    ║
╟───┼──────────────────────╢
║ 1 │ 3                    ║
╟───┼──────────────────────╢
║ 2 │ 5                    ║
╟───┼──────────────────────╢
║ 3 │ undefined            ║
╟───┼──────────────────────╢
║ 4 │ 6                    ║
╟───┼──────────────────────╢
║ 5 │ 8                    ║
╚═══╧══════════════════════╝
```

Creating a [`Series`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.html#pandas.Series) from a tensor

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
const tf = require("@tensorflow/tfjs-node")


let tensor_arr = tf.tensor([12,34,56,2])
let s = new dfd.Series(tensor_arr)
s.print()
```
{% endtab %}

{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>

    <title>Document</title>
</head>

<body>

    <script>
        const tf = dfd.tf //get tensorflow lib from danfo
        let tensor_arr = tf.tensor([12,34,56,2])
        let s = new dfd.Series(tensor_arr)
        s.print()

    </script>

</body>

</html>
```
{% endtab %}
{% endtabs %}

```
╔═══╤════╗
║ 0 │ 12 ║
╟───┼────╢
║ 1 │ 34 ║
╟───┼────╢
║ 2 │ 56 ║
╟───┼────╢
║ 3 │ 2  ║
╚═══╧════╝
```

Creating a [`DataFrame`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html#pandas.DataFrame) by passing a JSON object:

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
<script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>    <title>Document</title>
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

Creating a [`DataFrame`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html#pandas.DataFrame) from a 2D tensor

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
const tf = require("@tensorflow/tfjs-node")


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
<script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>    <title>Document</title>
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

Creating a [`DataFrame`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html#pandas.DataFrame) by passing a dictionary of objects with the same length

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


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
<script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>    <title>Document</title>
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

The columns of the resulting [`DataFrame`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html#pandas.DataFrame) have different [dtypes](https://pandas.pydata.org/pandas-docs/stable/user_guide/basics.html#basics-dtypes).

```javascript
df.ctypes.print()
```

```
//output
╔═══╤═════════╗
║ A │ string  ║
╟───┼─────────╢
║ B │ string  ║
╟───┼─────────╢
║ C │ int32   ║
╟───┼─────────╢
║ D │ float32 ║
╟───┼─────────╢
║ E │ string  ║
╚═══╧═════════╝
```

Creating a [`DataFrame`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html#pandas.DataFrame) by passing an array of arrays. Index and column labels are automatically generated for you.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

arr_data = [["bval1", 10, 1.2, "test"],
            ["bval2", 20, 3.45, "train"],
            ["bval3", 30, 60.1, "train"],
            ["bval4", 35, 3.2, "test"]]

df = new dfd.DataFrame(arr_data)
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
<script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>    <title>Document</title>
</head>

<body>

    <script>

        arr_data = [["bval1", 10, 1.2, "test"],
            ["bval2", 20, 3.45, "train"],
            ["bval3", 30, 60.1, "train"],
            ["bval4", 35, 3.2, "test"]]

        df = new dfd.DataFrame(arr_data)
        df.print()

    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

```
//output in console

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ 0                 │ 1                 │ 2                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ bval1             │ 10                │ 1.2               │ test              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ bval2             │ 20                │ 3.45              │ train             ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ bval3             │ 30                │ 60.1              │ train             ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ bval4             │ 35                │ 3.2               │ test              ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

### Viewing data

Here is how to view the top and bottom rows of the frame above:

```
df.head(2).print()
df.tail(2).print()
```

```
//output from head
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ 0                 │ 1                 │ 2                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ bval1             │ 10                │ 1.2               │ test              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ bval2             │ 20                │ 3.45              │ train             ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝


//output from tail

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ 0                 │ 1                 │ 2                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ bval3             │ 30                │ 60.1              │ train             ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ bval4             │ 35                │ 3.2               │ test              ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Display the index, columns:

{% tabs %}
{% tab title="JavaScript" %}
```javascript
const dfd = require("danfojs-node")

dates = new dfd.date_range({ start: '2017-01-01', end: "2020-01-01", period: 4, freq: "Y" })


obj_data = {'A': dates,
            'B': ["bval1", "bval2", "bval3", "bval4"],
            'C': [10, 20, 30, 40],
            'D': [1.2, 3.45, 60.1, 45],
            'E': ["test", "train", "test", "train"]
            }

df = new dfd.DataFrame(obj_data)

console.log(df.index);
console.log(df.columns);
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
<script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>    <title>Document</title>
</head>

<body>

    <script>

       dates = new dfd.date_range({ start: '2017-01-01', end: "2020-01-01", period: 4, freq: "Y" })


        obj_data = {'A': dates,
                    'B': ["bval1", "bval2", "bval3", "bval4"],
                    'C': [10, 20, 30, 40],
                    'D': [1.2, 3.45, 60.1, 45],
                    'E': ["test", "train", "test", "train"]
                    }

        df = new dfd.DataFrame(obj_data)

        console.log(df.index);
        console.log(df.columns);

    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

```
//output
[ 0, 1, 2, 3 ]
[ 'A', 'B', 'C', 'D', 'E' ]
```

[`DataFrame.tensor`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_numpy.html#pandas.DataFrame.to_numpy) returns a Tensorflow tensor representation of the underlying data. Note that **Tensorflow tensors have one dtype for the entire array, while danfo DataFrames have one dtype per column**.

For `df`, our [`DataFrame`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html#pandas.DataFrame) of all floating-point values, [`DataFrame.tensor`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_numpy.html#pandas.DataFrame.to_numpy)is fast and doesn’t require copying data.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


json_data = [{ A: 0.4612, B: 4.28283, C: -1.509, D: -1.1352 },
{ A: 0.5112, B: -0.22863, C: -3.39059, D: 1.1632 },
{ A: 0.6911, B: -0.82863, C: -1.5059, D: 2.1352 },
{ A: 0.4692, B: -1.28863, C: 4.5059, D: 4.1632 }]

df = new dfd.DataFrame(json_data)

console.log(df.tensor);
//or
df.tensor.print()
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
<script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>    <title>Document</title>
</head>

<body>

    <script>

        json_data = [{ A: 0.4612, B: 4.28283, C: -1.509, D: -1.1352 },
        { A: 0.5112, B: -0.22863, C: -3.39059, D: 1.1632 },
        { A: 0.6911, B: -0.82863, C: -1.5059, D: 2.1352 },
        { A: 0.4692, B: -1.28863, C: 4.5059, D: 4.1632 }]

        df = new dfd.DataFrame(json_data)

        console.log(df.tensor);
        //or
        df.tensor.print()

    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

```
//output

Tensor {
  kept: false,
  isDisposedInternal: false,
  shape: [ 4, 4 ],
  dtype: 'float32',
  size: 16,
  strides: [ 4 ],
  dataId: {},
  id: 0,
  rankType: '2'
}

Tensor
    [[0.4612, 4.2828302, -1.5089999, -1.1352  ],
     [0.5112, -0.22863 , -3.39059  , 1.1632   ],
     [0.6911, -0.82863 , -1.5059   , 2.1352   ],
     [0.4692, -1.28863 , 4.5058999 , 4.1631999]]
```

**Note**

[`DataFrame.tensor`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_numpy.html#pandas.DataFrame.to_numpy) does _not_ include the index or column labels in the output.

[`describe()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.describe.html#pandas.DataFrame.describe) shows a quick statistic summary of your data:

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


json_data = [{ A: 0.4612, B: 4.28283, C: -1.509, D: -1.1352 },
{ A: 0.5112, B: -0.22863, C: -3.39059, D: 1.1632 },
{ A: 0.6911, B: -0.82863, C: -1.5059, D: 2.1352 },
{ A: 0.4692, B: -1.28863, C: 4.5059, D: 4.1632 }]

df = new dfd.DataFrame(json_data)

df.describe().print()
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
<script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>    <title>Document</title>
</head>

<body>

    <script>

        json_data = [{ A: 0.4612, B: 4.28283, C: -1.509, D: -1.1352 },
                    { A: 0.5112, B: -0.22863, C: -3.39059, D: 1.1632 },
                    { A: 0.6911, B: -0.82863, C: -1.5059, D: 2.1352 },
                    { A: 0.4692, B: -1.28863, C: 4.5059, D: 4.1632 }]

        df = new dfd.DataFrame(json_data)

        df.describe().print()

    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

```
//output in console

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 │ D                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ count      │ 4                 │ 4                 │ 4                 │ 4                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ mean       │ 0.533175          │ 0.4842349999999…  │ -0.474897500000…  │ 1.5816            ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ std        │ 0.1075428712963…  │ 2.5693167249095…  │ 3.4371471031498…  │ 2.2005448052698…  ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ min        │ 0.4612            │ -1.28863          │ -3.39059          │ -1.1352           ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ median     │ 0.4901999999999…  │ -0.528629999999…  │ -1.50745          │ 1.6492            ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ max        │ 0.6911            │ 4.28283           │ 4.5059            │ 4.1632            ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ variance   │ 0.0115654691666…  │ 6.6013884328999…  │ 11.813980208691…  │ 4.84239744        ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Sorting by values (Defaults to ascending):

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = {"A": [-20, 30, 47.3, NaN],
             "B": [34, -4, 5, 6] ,
             "C": [20, 2, 3, 30] }


let df = new dfd.DataFrame(data)
df.sort_values({by: "C", inplace: true})
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
<script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>    <title>Document</title>
</head>

<body>

    <script>

        let data = {"A": [-20, 30, 47.3, NaN],
             "B": [34, -4, 5, 6] ,
             "C": [20, 2, 3, 30] }


        let df = new dfd.DataFrame(data)
        df.sort_values({by: "C", inplace: true})
        df.print()

    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ 30                │ -4                │ 2                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ 47.3              │ 5                 │ 3                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ -20               │ 34                │ 20                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ NaN               │ 6                 │ 30                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

### Selection

#### Getting

Selecting a single column, which yields a [`Series`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.html#pandas.Series), equivalent to `df.A`:

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")


json_data = [{ A: 0.4612, B: 4.28283, C: -1.509, D: -1.1352 },
{ A: 0.5112, B: -0.22863, C: -3.39059, D: 1.1632 },
{ A: 0.6911, B: -0.82863, C: -1.5059, D: 2.1352 },
{ A: 0.4692, B: -1.28863, C: 4.5059, D: 4.1632 }]

df = new dfd.DataFrame(json_data)

df['A'].print()
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
<script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>    <title>Document</title>
</head>

<body>

    <script>


        json_data = [{ A: 0.4612, B: 4.28283, C: -1.509, D: -1.1352 },
                    { A: 0.5112, B: -0.22863, C: -3.39059, D: 1.1632 },
                    { A: 0.6911, B: -0.82863, C: -1.5059, D: 2.1352 },
                    { A: 0.4692, B: -1.28863, C: 4.5059, D: 4.1632 }]

        df = new dfd.DataFrame(json_data)

        df['A'].print()

    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

```
//output
╔═══╤══════════════════════╗
║   │ A                    ║
╟───┼──────────────────────╢
║ 0 │ 0.4612               ║
╟───┼──────────────────────╢
║ 1 │ 0.5112               ║
╟───┼──────────────────────╢
║ 2 │ 0.6911               ║
╟───┼──────────────────────╢
║ 3 │ 0.4692               ║
╚═══╧══════════════════════╝
```

#### Selection by label

For getting a cross-section using a label:

```javascript
const dfd = require("danfojs")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"] ,
            "Count": [21, 5, 30, 10] ,
           "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data, {index: ["a", "b", "c", "d"]})
df.print()

let sub_df = df.loc({rows: ["a", "c"]})
sub_df.print()
```

```
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ a │ Apples            │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ b │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ c │ Banana            │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ d │ Pear              │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


 Shape: (2,3) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ a │ Apples            │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ c │ Banana            │ 30                │ 40                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Selecting on a multi-axis by label:

```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"] ,
            "Count": [21, 5, 30, 10],
             "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data)
df.print()

let sub_df = df.loc({ rows: [0,1], columns: ["Name", "Price"] })
sub_df.print()
```

```
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ Apples            │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ Banana            │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ Pear              │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


 Shape: (2,2) 

╔═══╤═══════════════════╤═══════════════════╗
║   │ Name              │ Price             ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ Apples            │ 200               ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ Mango             │ 300               ║
╚═══╧═══════════════════╧═══════════════════╝
```

Showing label slicing:

```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"] ,
            "Count": [21, 5, 30, 10],
             "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data)
df.print()

let sub_df = df.loc({ rows: ["0:2"], columns: ["Name", "Price"] })
sub_df.print()
```

```
//before slicing
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ Apples            │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ Banana            │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ Pear              │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝

//after slicing
 

╔════════════╤═══════════════════╤═══════════════════╗
║            │ Name              │ Price             ║
╟────────────┼───────────────────┼───────────────────╢
║ 0          │ Apples            │ 200               ║
╟────────────┼───────────────────┼───────────────────╢
║ 1          │ Mango             │ 300               ║
╚════════════╧═══════════════════╧═══════════════════╝
```

#### Selection by position

Select via the position of the passed integers:

```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"] ,
           "Count": [21, 5, 30, 10] ,
           "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data)

let sub_df = df.iloc({rows: [1,3]})
sub_df.print()
```

```
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ Pear              │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

By integer slices:

```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"] ,
           "Count": [21, 5, 30, 10] ,
           "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data)

let sub_df = df.iloc({rows: ["1:3"]})
sub_df.print()
```

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ Name              │ Count             │ Price             ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ Mango             │ 5                 │ 300               ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ Banana            │ 30                │ 40                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

By lists of integer position locations:

```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"] ,
           "Count": [21, 5, 30, 10] ,
           "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data)

let sub_df = df.iloc({rows: [1,3], columns: [0,2]})
sub_df.print()
```

```
╔═══╤═══════════════════╤═══════════════════╗
║   │ Name              │ Price             ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ Mango             │ 300               ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ Pear              │ 250               ║
╚═══╧═══════════════════╧═══════════════════╝
```

For slicing rows explicitly:

```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"] ,
           "Count": [21, 5, 30, 10] ,
           "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data)

let sub_df = df.iloc({rows: ["2:3"], columns: [":"]})
sub_df.print()
```

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ Name              │ Count             │ Price             ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ Banana            │ 30                │ 40                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

For slicing columns explicitly:

```javascript
const dfd = require("danfojs-node")

let data = { "Name": ["Apples", "Mango", "Banana", "Pear"] ,
           "Count": [21, 5, 30, 10] ,
           "Price": [200, 300, 40, 250] }

let df = new dfd.DataFrame(data)

let sub_df = df.iloc({rows: [":"], columns: ["1:2"]})
sub_df.print()
```

```
╔════════════╤═══════════════════╗
║            │ Count             ║
╟────────────┼───────────────────╢
║ 0          │ 21                ║
╟────────────┼───────────────────╢
║ 1          │ 5                 ║
╟────────────┼───────────────────╢
║ 2          │ 30                ║
╟────────────┼───────────────────╢
║ 3          │ 10                ║
╚════════════╧═══════════════════╝
```

#### Selection with Boolean Mask

You can select subsections from a DataFrame by a booelan condition mask. E.g. In the following code, we select and return only rows where the column `Count` is greater than 10. 

```javascript
let data = {
    "Name": ["Apples", "Mango", "Banana", "Pear"],
    "Count": [21, 5, 30, 10],
    "Price": [200, 300, 40, 250]
}

let df = new dfd.DataFrame(data)

let sub_df = df.iloc({ rows: df["Count"].gt(10) })
sub_df.print()
```

```
//output
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ Name              │ Count             │ Price             ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ Apples            │ 21                │ 200               ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ Banana            │ 30                │ 40                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

A Boolean mask for filtering also works for multiple conditions using `and` & `or` functions. E.g, In the following code, we select and return only rows where the column `Count` is greater than 10 and column `Name` is equal to `Apples`. 

```javascript
let sub_df = df.iloc({
    rows: df["Count"].gt(10).and(df["Name"].eq("Apples")),
    columns: [0]
})
sub_df.print()

//output
╔════════════╤═══════════════════╗
║            │ Name              ║
╟────────────┼───────────────────╢
║ 0          │ Apples            ║
╚════════════╧═══════════════════╝
```

#### Boolean Querying/Filtering

Using a single column’s values to select data.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]

let df = new dfd.DataFrame(data, { columns: cols })
df.print() //before query

let query_df = df.query({ "column": "B", "is": ">", "to": 5 })
query_df.print() //after query
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
<script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>    <title>Document</title>
</head>

<body>

    <script>


       let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
        let cols = ["A", "B", "C"]

        let df = new dfd.DataFrame(data, { columns: cols })
        df.print() //before query

        let query_df = df.query({ "column": "B", "is": ">", "to": 5 })
        query_df.print() //after query

    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

```
//before query
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 1                 │ 2                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 4                 │ 5                 │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 20                │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 39                │ 89                │ 78                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝

//after query
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 20                │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 39                │ 89                │ 78                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

The best way to query data is to use a boolean mask just as we demonstrated above with iloc and locs. For example, in the following code, we pass a condition parameter instead:

```javascript
let data = {
    "A": ["Ng", "Yu", "Mo", "Ng"],
    "B": [34, 4, 5, 6],
    "C": [20, 20, 30, 40]
}
let df = new dfd.DataFrame(data)

let query_df = df.query({ condition: df["B"].gt(5) })
query_df.print()
```

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ Ng                │ 34                │ 20                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ Ng                │ 6                 │ 40                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Querying by a boolean condition is supported from v0.3.0 and above. It also supports condition chaining as long as the final boolean mask is the same lenght as the DataFrame rows. For example in the following code, we use multiple chaining conditions:

```javascript
let data = {
    "A": ["Ng", "Yu", "Mo", "Ng"],
    "B": [34, 4, 5, 6],
    "C": [20, 20, 30, 40]
}
let query_df = df.query({
    condition:
        df["B"].gt(5).and(df["C"].lt(30))
})
query_df.print() //after query

//output
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ Ng                │ 34                │ 20                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝


```

#### Adding a new column

Setting a new column automatically aligns the data by the indexes.

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [30, 1, 2, 3] ,
             "B": [34, 4, 5, 6] ,
             "C": [20, 20, 30, 40] }

let df = new dfd.DataFrame(data)
df.print()

let new_col = [1, 2, 3, 4]
df.addColumn({ column: "D", values: new_col, inplace: true }); //happens inplace

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
<script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>    <title>Document</title>
</head>

<body>

    <script>


        let data = { "A": [30, 1, 2, 3] ,
             "B": [34, 4, 5, 6] ,
             "C": [20, 20, 30, 40] }

        let df = new dfd.DataFrame(data)
        df.print()

        let new_col = [1, 2, 3, 4]
        df.addColumn({ "column": "D", "values": new_col, inplace: true }); //happens inplace

        df.print()

    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

```
//before adding column
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 30                │ 34                │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 4                 │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 5                 │ 30                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 3                 │ 6                 │ 40                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝

//after adding column
 Shape: (4,3) 

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 │ D                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ 1                 │ 2                 │ 3                 │ 25                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ 4                 │ 5                 │ 6                 │ 35                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ 20                │ 30                │ 40                │ 45                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ 39                │ 89                │ 78                │ 55                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

### Missing data

 **NaN** represent missing data in Danfo.js. These values can be dropped or filled using some functions available in Danfo.js. 

To drop any rows that have missing data:

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = [[1, 2, 3], [NaN, 5, 6], [NaN, 30, 40], [39, 20, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

df.print()

let df_drop = df.dropna(0)
df_drop.print()
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
<script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>    <title>Document</title>
</head>

<body>

    <script>


        let data = [[1, 2, 3], [NaN, 5, 6], [NaN, 30, 40], [39, undefined, 78]]
        let cols = ["A", "B", "C"]
        let df = new dfd.DataFrame(data, { columns: cols })

        df.print()

        let df_drop = df.dropna({axis: 0})
        df_drop.print()

    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

```
//Before dropping
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ 1                 │ 2                 │ 3                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ NaN               │ 5                 │ 6                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ NaN               │ 30                │ 40                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ 39                │ 20                │ 78                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝


//after droppping
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ 1                 │ 2                 │ 3                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ 39                │ 20                │ 78                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

To drop any columns with have missing data, set the axis to 1:

```javascript
const dfd = require("danfojs-node")

let data = [[1, 2, 3], [NaN, 5, 6], [20, NaN, 40], [39, 34, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

df.print()

let df_drop = df.dropna(1)
df_drop.print()
```

```
//Before dropping
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ 1                 │ 2                 │ 3                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ NaN               │ 5                 │ 6                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ 20                │ NaN               │ 40                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ 39                │ 34                │ 78                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝


//after droppping

╔════════════╤═══════════════════╗
║            │ C                 ║
╟────────────┼───────────────────╢
║ 0          │ 3                 ║
╟────────────┼───────────────────╢
║ 1          │ 6                 ║
╟────────────┼───────────────────╢
║ 2          │ 40                ║
╟────────────┼───────────────────╢
║ 3          │ 78                ║
╚════════════╧═══════════════════╝

```

Filling missing data:

```javascript
const dfd = require("danfojs-node")


let data = {
    "Name": ["Apples", "Mango", "Banana", NaN],
    "Count": [NaN, 5, NaN, 10],
    "Price": [200, 300, 40, 250]
  }

let df = new dfd.DataFrame(data)
let df_filled = df.fillna("Apples")

df_filled.print()
```

```
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ Apples            │ Apples            │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ Banana            │ Apples            │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ Apples            │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Filling missing values in specific columns with specific values:

```javascript
const dfd = require("danfojs-node")

let data = {
    "Name": ["Apples", "Mango", "Banana", NaN],
    "Count": [NaN, 5, NaN, 10],
    "Price": [200, 300, 40, 250]
}

let df = new dfd.DataFrame(data)
df.print()

let df_filled = df.fillna(["Apples", df["Count"].mean()], { columns: ["Name", "Count"] })
df_filled.print()
```

```
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ Apples            │ 7.5               │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Mango             │ 5                 │ 300               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ Banana            │ 7.5               │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ Apples            │ 10                │ 250               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

To get the boolean mask where values are `nan`.

```javascript
const dfd = require("danfojs-node")

let data = {"Name":["Apples", "Mango", "Banana", undefined],
            "Count": [NaN, 5, NaN, 10], 
            "Price": [200, 300, 40, 250]}

let df = new dfd.DataFrame(data)
df.isna().print()
```

```
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ false             │ true              │ false             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ false             │ false             │ false             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ false             │ true              │ false             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ true              │ false             │ false             ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

### Operations

#### Stats

Operations, in general, _exclude_ missing data.

Performing a descriptive statistic:

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
cols = ["A", "B", "C"]


let df = new dfd.DataFrame(data, { columns: cols })
df.print()
df.mean().print() //defaults to column axis
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
<script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>    <title>Document</title>
</head>

<body>

    <script> 

    data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
    cols = ["A", "B", "C"]


    let df = new dfd.DataFrame(data)
    df.print()
    df.mean().print() //defaults to column axis

    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

```
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ 0                 │ 1                 │ 2                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 11                │ 20                │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 15                │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 2                 │ 89                │ 78                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝

╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ A │ 4                    ║
╟───┼──────────────────────╢
║ B │ 38.5                 ║
╟───┼──────────────────────╢
║ C │ 31.75                ║
╚═══╧══════════════════════╝
```

Same operation on the row axis:

```javascript
const dfd = require("danfojs-node")

data = [[11, 20, 3], [1, 15, 6], [2, 30, 40], [2, 89, 78]]
cols = ["A", "B", "C"]


let df = new dfd.DataFrame(data)
df.print()
df.mean(0).print() //row axis=0, column=1
```

```
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ 0                 │ 1                 │ 2                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 11                │ 20                │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 15                │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2                 │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 2                 │ 89                │ 78                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝

╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 11.333333015441895   ║
╟───┼──────────────────────╢
║ 1 │ 7.333333492279053    ║
╟───┼──────────────────────╢
║ 2 │ 24                   ║
╟───┼──────────────────────╢
║ 3 │ 56.33333206176758    ║
╚═══╧══════════════════════╝
```

Operations on objects with different dimensionality and need alignment. danfo automatically broadcasts along the specified dimension.

```javascript
const dfd = require("danfojs-node")


let data = { "Col1": [1, 4, 5, 1], "Col2": [3, 2, 0, 4] }
let df = new dfd.DataFrame(data)
let sf = new dfd.Series([4, 5])

let df_new = df.sub(sf, { axis: 1 })

df_new.print()
```

```
╔═══╤═══════════════════╤═══════════════════╗
║   │ Col1              │ Col2              ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ -3                │ -2                ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 0                 │ -3                ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 1                 │ -5                ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ -3                │ -1                ║
╚═══╧═══════════════════╧═══════════════════╝
```

#### Apply

Applying functions to the data along specified axis. If axis = 1 (default), then the specified function (`callable)` will be called with each column data, and vice versa:

```javascript
const dfd = require("danfojs")

let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

function sum_vals(col) {
    return col.reduce((a, b) => a + b, 0);
}

let df_new = df.apply(sum_vals, { axis: 1 })
df_new.print()
```

```
//before applying
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 1                 │ 2                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 4                 │ 5                 │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 20                │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 39                │ 89                │ 78                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


//after applying

╔═══╤═════╗
║ A │ 64  ║
╟───┼─────╢
║ B │ 126 ║
╟───┼─────╢
║ C │ 127 ║
╚═══╧═════╝
```

Applying Element wise operations to the data:

You can use the `apply_map` function if you need to apply a function to each element in the DataFrame. `apply_map` works element-wise. 

```javascript
const dfd = require("danfojs-node")

let data = [[1, 2, 3], [4, 5, 6], [20, 30, 40], [39, 89, 78]]
let cols = ["A", "B", "C"]
let df = new dfd.DataFrame(data, { columns: cols })

function sum_vals(x) {
    return x + 10
}

let df_new = df.apply_map(sum_vals)
df_new.print()
```

```
//before applying
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 1                 │ 2                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 4                 │ 5                 │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 20                │ 30                │ 40                ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 39                │ 89                │ 78                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝


 //after apply_map

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ A                 │ B                 │ C                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ 11                │ 12                │ 13                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ 14                │ 15                │ 16                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ 30                │ 40                │ 50                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ 49                │ 99                │ 88                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

#### String Methods

Series is equipped with a set of string processing methods in the **str** attribute that make it easy to operate on each element of the array, as in the code snippet below. Note that pattern-matching in **str** generally uses JavaScript [regular expressions](https://docs.python.org/3/library/re.html) by default (and in some cases always uses them).

```javascript
const dfd = require("danfojs-node")

s = new dfd.Series(['A', 'B', 'C', 'Aaba', 'Baca', 'CABA', 'dog', 'cat'])
lower_s = s.str.toLowerCase()
lower_s.print()
```

```
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ a                    ║
╟───┼──────────────────────╢
║ 1 │ b                    ║
╟───┼──────────────────────╢
║ 2 │ c                    ║
╟───┼──────────────────────╢
║ 3 │ aaba                 ║
╟───┼──────────────────────╢
║ 4 │ baca                 ║
╟───┼──────────────────────╢
║ 5 │ caba                 ║
╟───┼──────────────────────╢
║ 6 │ dog                  ║
╟───┼──────────────────────╢
║ 7 │ cat                  ║
╚═══╧══════════════════════╝
```

See more string [accessors](https://jsdata.gitbook.io/danfojs/api-reference/series#accessors) here

### Merge

#### Concat

danfo provides various methods for easily combining together Series and DataFrame objects with various kinds of set logic for the indexes and relational algebra functionality in the case of join / merge-type operations.

Concatenating DataFrame together with [`concat()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.concat.html#pandas.concat):

```javascript
const dfd = require("danfojs-node")


let data = [['K0', 'k0', 'A0', 'B0'], ['k0', 'K1', 'A1', 'B1'],
['K1', 'K0', 'A2', 'B2'], ['K2', 'K2', 'A3', 'B3']]

let data2 = [['K0', 'k0', 'C0', 'D0'], ['K1', 'K0', 'C1', 'D1'],
['K1', 'K0', 'C2', 'D2'], ['K2', 'K0', 'C3', 'D3']]

let colum1 = ['Key1', 'Key2', 'A', 'B']
let colum2 = ['Key1', 'Key2', 'A', 'D']

let df1 = new dfd.DataFrame(data, { columns: colum1 })
let df2 = new dfd.DataFrame(data2, { columns: colum2 })


let com_df = dfd.concat({ df_list: [df1, df2], axis: 1 }) //along column axis
com_df.print()
```

```
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Key1              │ Key2              │ A                 │ ...               │ Key1_2            │ Key2_2            │ A_2               │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ K0                │ k0                │ A0                │ ...               │ K0                │ k0                │ C0                │ D0                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ k0                │ K1                │ A1                │ ...               │ K1                │ K0                │ C1                │ D1                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ K1                │ K0                │ A2                │ ...               │ K1                │ K0                │ C2                │ D2                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ K2                │ K2                │ A3                │ ...               │ K2                │ K0                │ C3                │ D3                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Concatenate along row axis (0).

```javascript
const dfd = require("danfojs-node")


let data = [['K0', 'k0', 'A0', 'B0'], ['k0', 'K1', 'A1', 'B1'],
['K1', 'K0', 'A2', 'B2'], ['K2', 'K2', 'A3', 'B3']]

let data2 = [['K0', 'k0', 'C0', 'D0'], ['K1', 'K0', 'C1', 'D1'],
['K1', 'K0', 'C2', 'D2'], ['K2', 'K0', 'C3', 'D3']]

let colum1 = ['Key1', 'Key2', 'A', 'B']
let colum2 = ['Key1', 'Key2', 'A', 'D']

let df1 = new dfd.DataFrame(data, { columns: colum1 })
let df2 = new dfd.DataFrame(data2, { columns: colum2 })


let com_df = dfd.concat({ df_list: [df1, df2], axis: 0 }) //along row axis
com_df.print()
```

```
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Key1              │ Key2              │ A                 │ B                 │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ K0                │ k0                │ A0                │ B0                │ NaN               ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ k0                │ K1                │ A1                │ B1                │ NaN               ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ K1                │ K0                │ A2                │ B2                │ NaN               ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ K2                │ K2                │ A3                │ B3                │ NaN               ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ K0                │ k0                │ C0                │ NaN               │ D0                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 5 │ K1                │ K0                │ C1                │ NaN               │ D1                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 6 │ K1                │ K0                │ C2                │ NaN               │ D2                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 7 │ K2                │ K0                │ C3                │ NaN               │ D3                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

#### Join

SQL style merges. See the Pandas [Database style joining](https://pandas.pydata.org/pandas-docs/stable/user_guide/merging.html#merging-join) section for more info.

```javascript
const dfd = require("danfojs-node")

let data = [['K0', 'k0', 'A0', 'B0'], ['k0', 'K1', 'A1', 'B1'],
            ['K1', 'K0', 'A2', 'B2'], ['K2', 'K2', 'A3', 'B3']]

let data2 = [['K0', 'k0', 'C0', 'D0'], ['K1', 'K0', 'C1', 'D1'],
            ['K1', 'K0', 'C2', 'D2'], ['K2', 'K0', 'C3', 'D3']]

let colum1 = ['Key1', 'Key2', 'A', 'B']
let colum2 = ['Key1', 'Key2', 'A', 'D']

let df1 = new dfd.DataFrame(data, { columns: colum1 })
let df2 = new dfd.DataFrame(data2, { columns: colum2 })
df1.print()
df2.print()

let merge_df = dfd.merge({ "left": df1, "right": df2, "on": ["Key1"]})
merge_df.print()
```

```
 //first DataFrame
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Key1              │ Key2              │ A                 │ B                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ K0                │ k0                │ A0                │ B0                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ k0                │ K1                │ A1                │ B1                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ K1                │ K0                │ A2                │ B2                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ K2                │ K2                │ A3                │ B3                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝


 //Second DataFrame

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Key1              │ Key2              │ A                 │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ K0                │ k0                │ C0                │ D0                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ K1                │ K0                │ C1                │ D1                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ K1                │ K0                │ C2                │ D2                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ K2                │ K0                │ C3                │ D3                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝


 //After inner join on column 'Key1'

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Key1              │ Key2              │ A                 │ B                 │ Key2_1            │ A_1               │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ K0                │ k0                │ A0                │ B0                │ k0                │ C0                │ D0                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ K1                │ K0                │ A2                │ B2                │ K0                │ C1                │ D1                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ K1                │ K0                │ A2                │ B2                │ K0                │ C2                │ D2                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ K2                │ K2                │ A3                │ B3                │ K0                │ C3                │ D3                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

See the [merge](https://jsdata.gitbook.io/danfojs/api-reference/general-functions/danfo.merge) section for more examples

### Grouping

By “group by” we are referring to a process involving one or more of the following steps:

> * **Splitting** the data into groups based on some criteria
> * **Applying** a function to each group independently
> * **Combining** the results into a data structure

See the [Grouping section](api-reference/groupby/).

```javascript
const dfd = require("danfojs-node")

let data ={'A': ['foo', 'bar', 'foo', 'bar',
                'foo', 'bar', 'foo', 'foo'],
           'B': ['one', 'one', 'two', 'three',
                'two', 'two', 'one', 'three'],
           'C': [1,3,2,4,5,2,6,7],
           'D': [3,2,4,1,5,6,7,8]
        }

let df = new dfd.DataFrame(data)


let grp = df.groupby(["A"])

grp.get_groups(["foo"]).print()

grp.get_groups(["bar"]).print()
```

```
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 1                 │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ two               │ 2                 │ 4                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ foo               │ two               │ 5                 │ 5                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ foo               │ one               │ 6                 │ 7                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ foo               │ three             │ 7                 │ 8                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝


 Shape: (3,4) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ bar               │ one               │ 3                 │ 2                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ bar               │ three             │ 4                 │ 1                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ bar               │ two               │ 2                 │ 6                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Grouping and then applying the[`sum()`](api-reference/groupby/groupby.sum.md) function to the resulting groups.

```javascript
const dfd = require("danfojs-node")

let data ={'A': ['foo', 'bar', 'foo', 'bar',
                'foo', 'bar', 'foo', 'foo'],
           'B': ['one', 'one', 'two', 'three',
                'two', 'two', 'one', 'three'],
           'C': [1,3,2,4,5,2,6,7],
           'D': [3,2,4,1,5,6,7,8]
        }

let df = new dfd.DataFrame(data)


let grp = df.groupby(["A"])
grp.col(["C"]).sum().print()
```

```
╔═══╤═══════════════════╤═══════════════════╗
║   │ A                 │ C_sum             ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ foo               │ 21                ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ bar               │ 9                 ║
╚═══╧═══════════════════╧═══════════════════╝
```

Grouping by multiple columns forms a hierarchical index, and again we can apply the[`sum()`](api-reference/groupby/groupby.sum.md) function.

```javascript
const dfd = require("danfojs-node")

let data ={'A': ['foo', 'bar', 'foo', 'bar',
                'foo', 'bar', 'foo', 'foo'],
           'B': ['one', 'one', 'two', 'three',
                'two', 'two', 'one', 'three'],
           'C': [1,3,2,4,5,2,6,7],
           'D': [3,2,4,1,5,6,7,8]
        }

let df = new dfd.DataFrame(data)


let grp = df.groupby(["A","B"])
grp.col(["C"]).sum().print()
```

```
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C_sum             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ foo               │ one               │ 7                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ foo               │ two               │ 7                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ foo               │ three             │ 7                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ bar               │ one               │ 3                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ bar               │ two               │ 2                 ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 5 │ bar               │ three             │ 4                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```

### Time series

danfo provides a simple but powerful, and efficient functionality for working with DateTime data. See the **dt** [Accessors](https://jsdata.gitbook.io/danfojs/api-reference/series#accessors) section.

```javascript
const dfd = require("danfojs-node")

let data = new dfd.date_range({"start":'2018-01', freq:'M', period:3})
let sf = new dfd.Series(data)
//print series
sf.print()
//print month names
sf.dt.month_name().print()
```

```
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 1/1/2018, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 1 │ 2/1/2018, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 2 │ 3/1/2018, 1:00:00 AM ║
╚═══╧══════════════════════╝

╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ Jan                  ║
╟───┼──────────────────────╢
║ 1 │ Feb                  ║
╟───┼──────────────────────╢
║ 2 │ Mar                  ║
╚═══╧══════════════════════╝
```

More Examples:

```javascript
const dfd = require("danfojs-node")

let data = new dfd.date_range({"start":'2018-01', freq:'M', period:3})
let sf = new dfd.Series(data)
//print series
sf.print()
//print month names
sf.dt.weekdays().print()
```

```
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 1/1/2018, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 1 │ 2/1/2018, 1:00:00 AM ║
╟───┼──────────────────────╢
║ 2 │ 3/1/2018, 1:00:00 AM ║
╚═══╧══════════════════════╝

╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ Mon                  ║
╟───┼──────────────────────╢
║ 1 │ Thu                  ║
╟───┼──────────────────────╢
║ 2 │ Thu                  ║
╚═══╧════════════════════
```

### Plotting

See the [Plotting](api-reference/plotting/) docs.

We use [Plotly.js](https://plotly.com/javascript/) as our backend for plotting. This gives you the ability to make interactive plots from DataFrame and Series. Plotting only works in the browser version of danfo.js, and requires an HTML div to show plots.

**Update**: As of `v0.2.3`, we stopped bundling Danfojs with Plotly. This has greatly reduced bundle size by about 80%. See more details in the release notes here. In order to make Plots, you must explicitly add the Plotly CDN to your file as we show in the updated examples:

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <script src="https://cdn.plot.ly/plotly-1.2.0.min.js"></script> 
     <script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>
     <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

         dfd.read_csv("https://raw.githubusercontent.com/plotly/datasets/master/finance-charts-apple.csv")
            .then(df => {

                var layout = {
                    title: 'A financial charts',
                    xaxis: {
                        title: 'Date',
                    },
                    yaxis: {
                        title: 'Count',
                    }
                }

                new_df = df.set_index({ column: "Date" })
                new_df.plot("plot_div").line({ columns: ["AAPL.Open", "AAPL.High"], layout: layout })

            }).catch(err => {
                console.log(err);
            })

    </script>
</body>

</html>
```

![](<.gitbook/assets/newplot-29- (2).png>)

On a DataFrame, the [`plot()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.plot.html#pandas.DataFrame.plot)method exposes various [plot types](api-reference/plotting/). And by default, all columns are plotted unless specified otherwise.

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <script src="https://cdn.plot.ly/plotly-1.2.0.min.js"></script> 
     <script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

        df = new dfd.DataFrame({'pig': [20, 18, 489, 675, 1776],
                               'horse': [4, 25, 281, 600, 1900]}, {index: [1990, 1997, 2003, 2009, 2014]})
        df.plot("plot_div").line()

    </script>
</body>

</html>
```

![](<.gitbook/assets/newplot-2- (1) (1).png>)

### Getting data in/out

#### CSV

[Writing to a  CSV file.](api-reference/dataframe/dataframe.to_csv.md)

Convert any DataFrame to csv format. If a file path is specified, then the CSV is saved to the path, else it is returned as a string. 

```javascript
const dfd = require("danfojs-node")
let data = {
    "Abs": [20.2, 30, 47.3],
    "Count": [34, 4, 5],
    "country code": ["NG", "FR", "GH"]
}


let df = new dfd.DataFrame(data)

const csv = df.to_csv()
console.log(csv);
//output
Abs,Count,country code
20.2,34,NG
30,4,FR
47.3,5,GH


df.to_csv({filePath: "testOut.csv" }) //writes to file in Nodejs


df.to_csv({fileName: "testOut", download: true }) //downloads the file in browser version


```

```
Abs,Count,country code
20.2,34,NG
30,4,FR
47.3,5,GH
```

[Reading from a CSV file.](https://pandas.pydata.org/pandas-docs/stable/user_guide/io.html#io-read-csv-table)

The **read_csv** method can read CSV file from local disk, or over the internet. If the file is to be read from a local disk in Node environment, you have to prefix the full path name with a "**file://**" prefix. For instance, to read a CSV file at the path **/home/Desktop/titanic.csv**, you can do the following:

{% tabs %}
{% tab title="JavaScript" %}
```javascript
const dfd = require("danfojs")

dfd.read_csv("file:///home/Desktop/titanic.csv")
  .then(df => {

   //do something with the CSV file
   df.head().print()

  }).catch(err=>{
     console.log(err);
  })
```
{% endtab %}

{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>

    <script>

         dfd.read_csv("https://raw.githubusercontent.com/plotly/datasets/master/finance-charts-apple.csv")
            .then(df => {

                //do something like display descriptive statistics
                df.describe().print()

            }).catch(err => {
                console.log(err);
            })

    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

#### JSON

Writing to [JSON](api-reference/dataframe/dataframe.to_json.md) format

```javascript
const dfd = require("danfojs-node")

let data = {
          "Abs": [20.2, 30, 47.3],
          "Count": [34, 4, 5],
          "country code": ["NG", "FR", "GH"]
        }


let df = new dfd.DataFrame(data)

const json = df.to_json()
console.log(json);
//output
[
  { Abs: 20.2, Count: 34, 'country code': 'NG' },
  { Abs: 30, Count: 4, 'country code': 'FR' },
  { Abs: 47.3, Count: 5, 'country code': 'GH' }
]


const json = df.to_json({format: "row"})
console.log(json);
//output
{
  Abs: [ 20.2, 30, 47.3 ],
  Count: [ 34, 4, 5 ],
  'country code': [ 'NG', 'FR', 'GH' ]
}

```
