---
description: >-
  Reads a comma-separated values (CSV) file into DataFrame. Also supports
  iterating or breaking of file into chunks.
---

# danfo.read\_csv

> danfo.**read\_csv**\(source, chunk\) [\[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/io/reader.js#L21)\]

| **Parameters** | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| _**source**_: | str, path or URL  | Any valid string path is acceptable. The string could be a URL. Valid URL schemes include http, ftp, s3, gs, and file. For local file path, it should be prefixed with " **file://**", for example, "**file:///home/path/to/table.csv**". |  |
| **chunk**: |  int, optional | The number of rows of file to read. Useful for reading pieces of large files. |  |

**Returns:**

     ****_**Promise**_. Resolves to DataFrame

### Example

The **read\_csv** method can read csv file from local disk, or over the internet. If the file is to be read from a local disk in Node environment, you have to prefix the full path name with a "**file://**" prefix. For instance, to read a csv file at the path **/home/Desktop/user\_names.csv**, you can do the following:

{% tabs %}
{% tab title="Node.js" %}
```javascript
const dfd = require("danfojs-node")

dfd.read_csv("file:///home/Desktop/user_names.csv")
  .then(df => {
  
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
     <!--danfojs CDN -->
    <script src="https://cdn.jsdelivr.net/npm/danfojs@0.0.15/dist/index.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
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

**Reading Large Files**

For extremely large files, that cannot be fit in memory at once, you can read the top portion in chunks. For instance, this [dataset](http://eforexcel.com/wp/wp-content/uploads/2017/07/1500000%20Sales%20Records.7z) has over 1.5 million rows and will throw a memory error if you try to load everything at once. To read these type of files, you can load them in chunks using the chunks parameter in **read\_csv**

{% tabs %}
{% tab title="JavaScript" %}
```javascript
const dfd = require("danfojs-node")

//read the first 10000 rows
dfd.read_csv("file:///home/Desktop/bigdata.csv", chunk=10000)
  .then(df => {
  
   df.tail().print()

  }).catch(err=>{
      console.log(err);
  })
```
{% endtab %}

{% tab title="Browser" %}
```

```
{% endtab %}
{% endtabs %}

