---
description: >-
  Converts a DataFrame or Series to Excel file and write file to disk or
  download in browser.
---

# DataFrame.to_excel

> DataFrame.**to_excel**(options) [\[source](https://github.com/opensource9ja/danfojs/blob/e25010c26d9c423412613d820015a48ad03d5c6d/danfojs-node/src/io/io.excel.js#L97)]

| **Parameters** | Type              | Description                                                                                                                                                                                                                                                                                                                                                                                                                       | Default                                                                                                  |
| -------------- | ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| **options**    |  object, optional | <p> Configuration object: </p><p>{</p><p> <strong><code>filePath</code></strong>: Local file path to write the CSV file to. If not specified, the CSV will be returned as a string. Only needed in Nodejs version<br><strong><code>fileName</code></strong>: The name of the file to download as. Only needed in the browser environment. <br><strong><code>sheetName</code></strong>: Name to call the excel sheet. </p><p>}</p> | <p>{<br><strong>filePath</strong>: "./output.xlsx",<br><strong>sheetName</strong>: "Sheet1"<br><br>}</p> |

The **to_excel** function can be used to write out a DataFrame or Series to Excel (**.xlsx**) file. The output format will depend on the environment. In the following examples, we show you how to write/download an Excel file from Node and Browser environments.

### Convert DataFrame to Excel and write to file path

Writing an Excel file to a local file path is only supported in the Nodejs environment

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

df.to_excel({ filePath: "testOut.xlsx"});
```
{% endtab %}
{% endtabs %}

### Convert DataFrame to Excel and download the file in a browser

You can automatically convert and download an Excel file in a browser environment, by specifying a `fileName`. 

```javascript
let data = {
    Abs: [20.2, 30, 47.3],
    Count: [34, 4, 5],
    "country code": ["NG", "FR", "GH"],
};

let df = new dfd.DataFrame(data);

df.to_excel({ fileName: "testOut.xlsx"});
```
