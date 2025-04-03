---
description: Reads a JSON file from local or remote location into a DataFrame.
---

# danfo.readExcel

> danfo.**readExcel**(source, options)

| Parameters | Type   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ---------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| source     | string | **source** : string, URL or local file path to Excel file.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| options    | Object | <p>{</p><p><strong>sheet</strong> : string, (Optional) Name of the sheet which u want to parse. Default will be the first sheet.<br><strong>method</strong>: The HTTP method to use.</p><p><strong>headers</strong>: Additional headers to send with the request if reading JSON from remote url. Supports all the node-fetch options in Nodejs, and all fetch options in browsers.</p><p><strong>frameConfig</strong>: Optional arguments passed when creating the DataFrame. e.g column names, index. etc.</p><p><strong>parsingOptions</strong>: supports all xlsx options. See <a href="https://docs.sheetjs.com/docs/api/parse-options">https://docs.sheetjs.com/docs/api/parse-options</a></p><p>}</p> |

### Example

The **readExcel** method can read excel files saved on a local disk, or over the internet.

{% tabs %}
{% tab title="Node.js" %}
```javascript
const dfd = require("danfojs-node")
const path = require("path")

let local_xcel = path.join(process.cwd(), "data", "testexcel.xlxs")

async function load_process_data() {
    let df = await dfd.readExcel(local_xcel)
    df.head().print()
}

load_process_data()
```
{% endtab %}

{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <script src="https://cdn.jsdelivr.net/npm/danfojs@1.2.0/lib/bundle.min.js"></script>
     <title>Document</title>
</head>

<body>

    <script>

        const remote_url = 'https://file-examples-com.github.io/uploads/2017/02/file_example_XLS_100.xls';
        dfd.readExcel(remote_url).then(df => {
            df.head().print()
        })

         
    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

### **Reading an input file object in the browser**

By specifying a valid [file object](https://developer.mozilla.org/en-US/docs/Web/API/File), you can load Excel files in the browser in DataFrames/Series

{% tabs %}
{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <script src="https://cdn.jsdelivr.net/npm/danfojs@1.2.0/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>
    <input type="file" id="file" name="file">
    <script>
        const inputFile = document.querySelector('#file')
        
        inputFile.addEventListener("change", async () => {
            const excelFile = inputFile.files[0]
            dfd.readExcel(excelFile).then((df) => {
                df.print()
            })
        })
         
    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}
