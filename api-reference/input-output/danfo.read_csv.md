---
description: >-
  Reads a comma-separated values (CSV) file into DataFrame. Also supports the
  reading of CSV files in chunks.
---

# danfo.read\_csv

> danfo.**read\_csv**\(source, configs\) [\[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/io/reader.js#L21)\]

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Parameters</b>
      </th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Default</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><em><b>source</b></em>:</td>
      <td style="text-align:left">str, path or URL</td>
      <td style="text-align:left">Any valid string path is acceptable. The string could be a URL or a valid
        local file path.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>configs</b>:</td>
      <td style="text-align:left">object, optional</td>
      <td style="text-align:left">
        <p></p>
        <p>Supports all Papaparse config parameters. See <a href="https://www.papaparse.com/docs#config">https://www.papaparse.com/docs#config</a>.</p>
        <p></p>
        <p>We set the following params by default:</p>
        <p><b>dynamicTyping: true</b>
        </p>
        <p><b>header: true</b>
        </p>
      </td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

**Returns:**

     ****_**Promise**_. Resolves to DataFrame

### Example

The **read\_csv** method can read a csv file from local disk, or over the internet \(URL\). Reading of local files are only supported in danfojs-node. 

{% tabs %}
{% tab title="Node.js" %}
```javascript
const dfd = require("danfojs-node")

dfd.read_csv("user_names.csv") //assumes file is in CWD
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
    <script src="https://cdn.plot.ly/plotly-1.2.0.min.js"></script> 
     <script src="https://cdn.jsdelivr.net/npm/danfojs@0.2.4/lib/bundle.min.js"></script>
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

**Loading Files from URL**

By specifying a valid URL, you can load CSV files from any location into Danfo**'**s data structure:

{% tabs %}
{% tab title="Node.js" %}
```javascript
const dfd = require("danfojs-node")

dfd.read_csv("https://raw.githubusercontent.com/plotly/datasets/master/finance-charts-apple.csv") //assumes file is in CWD
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
    <script src="https://cdn.plot.ly/plotly-1.2.0.min.js"></script> 
     <script src="https://cdn.jsdelivr.net/npm/danfojs@0.2.4/lib/bundle.min.js"></script>
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



