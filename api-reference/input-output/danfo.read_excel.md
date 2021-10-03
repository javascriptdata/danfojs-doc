---
description: Reads an excel file into DataFrame.
---

# danfo.read\_excel

> danfo.**read\_excel**\(source, configs\) [\[source](https://github.com/opensource9ja/danfojs/blob/849d14c8e7fa79bce4ffa9d0d177639047313520/danfojs/src/io/reader.js#L89)\]

> <table>
>   <thead>
>     <tr>
>       <th style="text-align:left">Parameters</th>
>       <th style="text-align:left">Type</th>
>       <th style="text-align:left">Description</th>
>     </tr>
>   </thead>
>   <tbody>
>     <tr>
>       <td style="text-align:left">source</td>
>       <td style="text-align:left">string</td>
>       <td style="text-align:left"><b>source</b> : string, URL or local file path to retreive Excel file.</td>
>     </tr>
>     <tr>
>       <td style="text-align:left">configs</td>
>       <td style="text-align:left">Object</td>
>       <td style="text-align:left">
>         <p>{</p>
>         <p><b>sheet</b> : string, (Optional) Name of the sheet which u want to parse.
>           Default will be the first sheet.
>           <br /><b>method</b>: The HTTP method to use.</p>
>         <p><b>headers</b>: Additional headers to send with the request if reading
>           JSON from remote url. Supports all the node-fetch options in Nodejs, and
>           all fetch options in browsers.</p>
>         <p>}</p>
>       </td>
>     </tr>
>   </tbody>
> </table>
>
> **Returns:**
>
>        ****return ****{**Promise**} DataFrame structure of parsed Excel data

### Example

The **read\_excel** method can read excel files saved on a local disk, or over the internet.

{% tabs %}
{% tab title="Node.js" %}
```javascript
const dfd = require("danfojs-node")
const path = require("path")

let local_xcel = path.join(process.cwd(), "data", "testexcel.xlxs")

async function load_process_data() {
    let df = await dfd.read_excel(local_xcel)
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
     <script src="https://cdn.jsdelivr.net/npm/danfojs@0.2.4/lib/bundle.min.js"></script>
     <title>Document</title>
</head>

<body>

    <script>

        const remote_url = 'https://file-examples-com.github.io/uploads/2017/02/file_example_XLS_100.xls';
        dfd.read_excel(remote_url).then(df => {
            df.head().print()
        })

         
    </script>
</body>

</html>

```
{% endtab %}
{% endtabs %}

