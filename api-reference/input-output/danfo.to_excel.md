---
description: >-
  Converts a DataFrame or Series to Excel file, and write file to disk or
  download in browser.
---

# danfo.toExcel

> danfo.**toExcel**(data, options)

| **Parameters** | Type                | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | Default                                                                                                  |
| -------------- | ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| _**data**_     | Series or DataFrame | The Series or DataFrame to write to CSV                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |                                                                                                          |
| **options**    | object, optional    | <p>Configuration object:</p><p>{</p><p><strong><code>filePath</code></strong>: Local file path to write the CSV file to. If not specified, the CSV will be returned as a string. Only needed in Nodejs version<br><strong><code>fileName</code></strong>: The name of the file to download as. Only needed in the browser environment.<br><strong><code>sheetName</code></strong>: Name to call the excel sheet.</p><p><strong>writingOptions</strong>: Supports all xlsx write options. See <a href="https://docs.sheetjs.com/docs/api/write-options">https://docs.sheetjs.com/docs/api/write-options</a></p><p>}</p> | <p>{<br><strong>filePath</strong>: "./output.xlsx",<br><strong>sheetName</strong>: "Sheet1"<br><br>}</p> |

The **toExcel** function can be used to write out a DataFrame or Series to Excel (**.xlsx**) file. The output format will depend on the environment. In the following examples, we show you how to write/download an Excel file from Node and Browser environments.

### Convert DataFrame to Excel and write to file path

You can write a DataFrame or Series in Excel format using the toExcel function and specifying the file path.&#x20;

{% tabs %}
{% tab title="Node.js" %}
```javascript
const dfd = require("danfojs-node")

let data = {
    Abs: [20.2, 30, 47.3],
    Count: [34, 4, 5],
    "country code": ["NG", "FR", "GH"],
};

let df = new dfd.DataFrame(data);

dfd.toExcel(df, { filePath: "testOut.xlsx"});
```
{% endtab %}
{% endtabs %}

### Convert DataFrame to Excel and download the file in Client-side lib

You can automatically convert and download an Excel file in a browser environment, by specifying a filename. This will open a download window.&#x20;

```javascript
let data = {
    Abs: [20.2, 30, 47.3],
    Count: [34, 4, 5],
    "country code": ["NG", "FR", "GH"],
};

let df = new DataFrame(data);

dfd.toExcel(df, { fileName: "testOut.xlsx"});
```
