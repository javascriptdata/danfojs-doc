---
description: Reads a JSON file into DataFrame.
---

# danfo.readJSON

> danfo.readJSON(source, options)

|                |                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                                                 |
| -------------- | -------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------- |
| **Parameters** | Type                                               | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                | Default                                         |
| _**source**_   | Input file object, string file\*\* \*\*path or URL | <p>Any valid string path is acceptable. The string could be a URL. Valid URL schemes include http, https, ftp, s3, gs, or a local path. Both relative and absolute paths are supported</p><p>An input file object is also supported in the browser.</p>                                                                                                                                                                                                                    |                                                 |
| options        | Object                                             | <p>Configuration options for reading JSON files. Supported options:</p><p>{<br><code>method</code>: The HTTP method to use.</p><p><code>headers</code>: Additional headers to send with the request if reading JSON from remote url. Supports all the <a href="https://github.com/node-fetch/node-fetch#options">node-fetch options</a> in Nodejs, and all <a href="https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API">fetch options</a> in browsers.</p><p>}</p> | <p>{<br><strong>method</strong>: "GET"<br>}</p> |

The **readJSON** method can read JSON files from a local disk, over the internet, or directly from input file objects.

### **Reading JSON files from local disk**

{% tabs %}
{% tab title="Node.js" %}
```javascript
const dfd = require("danfojs-node")

dfd.readJSON("./user_names.json")
  .then(df => {
  
   df.head().print()

  }).catch(err=>{
     console.log(err);
  })
```
{% endtab %}
{% endtabs %}

### **Reading JSON files from a URL**

By specifying a valid URL, you can load JSON files from any location:

{% tabs %}
{% tab title="Node.js" %}
```javascript
const dfd = require("danfojs-node")

dfd.readJSON("https://raw.githubusercontentdatasets/master/finance-charts-apple.json") 
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
     <script src="https://cdn.jsdelivr.net/npm/danfojs@1.1.0/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>

    <script>
     
     dfd.readJSON("https://raw.githubusercontentdatasets/master/finance-charts-apple.json") 
       .then(df => {
       
        df.head().print()
     
       }).catch(err=>{
          console.log(err);
       })
         
    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

### **Reading an input file object in the browser**

By specifying a valid [file object](https://developer.mozilla.org/en-US/docs/Web/API/File), you can load a JSON file in the browser:

{% tabs %}
{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <script src="https://cdn.jsdelivr.net/npm/danfojs@1.1.0/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>
    <input type="file" id="file" name="file">
    <script>
            
        inputFile.addEventListener("change", async () => {
            const jsonFile = inputFile.files[0]
            dfd.readJSON(jsonFile).then((df) => {
                df.print()
            })
        })
         
    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}
