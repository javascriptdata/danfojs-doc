---
description: Reads an excel file into DataFrame.
---

# danfo.read\_excel

> danfo.**read\_excel**\(kwargs\) [\[source](https://github.com/opensource9ja/danfojs/blob/849d14c8e7fa79bce4ffa9d0d177639047313520/danfojs/src/io/reader.js#L89)\]

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
>       <td style="text-align:left">kwargs</td>
>       <td style="text-align:left">Object</td>
>       <td style="text-align:left">
>         <p>{</p>
>         <p><b>source</b>: string, URL or local file path to retreive Excel file.</p>
>         <p><b>sheet_name</b>: string, (Optional) Name of the sheet which u want to
>           parse. Default will be the first sheet.</p>
>         <p><b>header_index</b>: int, (Optional) Index of the row which represents
>           the header(columns) of the data. Default will be the first non empty row.</p>
>         <p><b>data_index</b>:<b> </b>int, (Optional)Index of the row from which actual
>           data(content) starts. Default will be the next row of <code>header_index</code>
>         </p>
>         <p>}</p>
>       </td>
>     </tr>
>   </tbody>
> </table>
>
> **Returns:**
>
>        ****return **DataFrame**

### Example

The **read\_excel** method can read excel files saved from local disk, or over the internet.

{% tabs %}
{% tab title="Node.js" %}
```javascript
const dfd = require("danfojs-node")

local_xcel = 'testexcel.xls'

async function load_process_data() {
    let df = await dfd.read_excel({source: local_xcel})
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
     <!--danfojs CDN -->
    <script src="https://cdn.jsdelivr.net/gh/opensource9ja/danfojs@latest/lib/bundle.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

        const remote_url = 'https://file-examples-com.github.io/uploads/2017/02/file_example_XLS_100.xls';
        dfd.read_excel({ source: remote_url }).then(df => {
            df.head().plot("plot_div").table()
        })

         
    </script>
</body>

</html>

```
{% endtab %}
{% endtabs %}

