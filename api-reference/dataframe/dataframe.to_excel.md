---
description: >-
  Converts a DataFrame or Series to Excel file and write file to disk or
  download in browser.
---

# DataFrame.toExcel

{% hint style="danger" %}
Deprecated in v1.1.0: Use the [`dfd.toExcel`](../input-output/danfo.to\_excel.md) function directly instead
{% endhint %}

> DataFrame.toExcel(options)

| **Parameters** | Type             | Description                                                                                                                                                                                                                                                                                                                                                                                                                | Default                                                                                                  |
| -------------- | ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| **options**    | object, optional | <p>Configuration object:</p><p><strong><code>filePath</code></strong>: Local file path to write the CSV file to. If not specified, the CSV will be returned as a string. Only needed in Nodejs version</p><p><br><strong><code>fileName</code></strong>: The name of the file to download as. Only needed in the browser environment.</p><p><br><strong><code>sheetName</code></strong>: Name to call the excel sheet.</p> | <p>{<br><strong>filePath</strong>: "./output.xlsx",<br><strong>sheetName</strong>: "Sheet1"<br><br>}</p> |

The **toExcel** function can be used to write out a DataFrame or Series to Excel (**.xlsx**) file. The output format will depend on the environment. In the following examples, we show you how to write/download an Excel file from Node and Browser environments.

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

df.toExcel({ filePath: "testOut.xlsx"});
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

df.toExcel({ fileName: "testOut.xlsx", download: true });
```
