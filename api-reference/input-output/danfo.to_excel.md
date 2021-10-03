---
description: >-
  Converts a DataFrame or Series to Excel file and write file to disk or
  download in browser.
---

# danfo.to\_excel

> danfo.**to\_excel**\(source, configs\) [\[source](https://github.com/opensource9ja/danfojs/blob/e25010c26d9c423412613d820015a48ad03d5c6d/danfojs-node/src/io/io.excel.js#L97)\]

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
      <td style="text-align:left"><em><b>data</b></em>
      </td>
      <td style="text-align:left">Series or DataFrame</td>
      <td style="text-align:left">The Series or DataFrame to write to CSV</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>options</b>
      </td>
      <td style="text-align:left">object, optional</td>
      <td style="text-align:left">
        <p>Configuration object:</p>
        <p>{</p>
        <p> <b><code>filePath</code></b>: Local file path to write the CSV file to.
          If not specified, the CSV will be returned as a string. Only needed in
          Nodejs version
          <br /><b><code>fileName</code></b>: The name of the file to download as. Only
          needed in the browser environment.
          <br /><b><code>sheetName</code></b>: Name to call the excel sheet.</p>
        <p>}</p>
      </td>
      <td style="text-align:left">{
        <br /><b>filePath</b>: &quot;./output.xlsx&quot;,
        <br /><b>sheetName</b>: &quot;Sheet1&quot;
        <br />
        <br />}</td>
    </tr>
  </tbody>
</table>

The **to\_excel** function can be used to write out a DataFrame or Series to Excel \(**.xlsx**\) file. The output format will depend on the environment. In the following examples, we show you how to write/download an Excel file from Node and Browser environments.

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

