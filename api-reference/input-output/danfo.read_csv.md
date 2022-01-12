---
description: >-
  Reads a comma-separated values (CSV) file into DataFrame. Also supports the
  reading of CSV files in chunks.
---

# danfo.readCSV

> danfo.**readCSV**(source, options)&#x20;

|                |                             |                                                                                                                                                                                                                            |                                                                       |
| -------------- | --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| **Parameters** | Type                        | Description                                                                                                                                                                                                                | Default                                                               |
| _**source**_   | File object, File path, URL | <p>Any valid string path is acceptable. The string could be a URL or a valid local file path.</p><p>A browser <a href="https://developer.mozilla.org/en-US/docs/Web/API/File">input file object</a> is also supported.</p> |                                                                       |
| **options**    | object, optional            | Supports all Papaparse config parameters. See [https://www.papaparse.com/docs#config](https://www.papaparse.com/docs#config).                                                                                              | <p><strong>{</strong></p><p><strong>header:</strong> true</p><p>}</p> |

The **readCSV** method can read a CSV file from a local disk, or over the internet (URL). Reading of local files is only supported in Nodejs, while reading of input file objects is only supported in the browser.

### **Reading files from local disk**

By specifying a valid file path, you can load CSV files from local disk:

{% tabs %}
{% tab title="Node.js" %}
```javascript
const dfd = require("danfojs-node")

dfd.readCSV("./user_names.csv") //assumes file is in CWD
  .then(df => {
  
   df.head().print()

  }).catch(err=>{
     console.log(err);
  })
```
{% endtab %}
{% endtabs %}

### **Reading files from a URL**

By specifying a valid URL, you can load CSV files from any location into Danfo\*\*'\*\*s data structure:

{% tabs %}
{% tab title="Node.js" %}
```javascript
const dfd = require("danfojs-node")

dfd.readCSV("https://raw.githubusercontent.com/plotly/datasets/master/finance-charts-apple.csv") //assumes file is in CWD
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
    <script src="https://cdn.plot.ly/plotly-2.2.0.min.js"></script> 
     <script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

         dfd.readCSV("https://raw.githubusercontent.com/plotly/datasets/master/finance-charts-apple.csv")
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

### **Reading an input file object in the browser**

By specifying a valid [file object](https://developer.mozilla.org/en-US/docs/Web/API/File), you can load CSV files in the browser in DataFrames/Series

{% tabs %}
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
    <input type="file" id="file" name="file">
    <script>
            
        inputFile.addEventListener("change", async () => {
            const csvFile = inputFile.files[0]
            dfd.readCSV(csvFile).then((df) => {
                df.print()
            })
        })
         
    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}
