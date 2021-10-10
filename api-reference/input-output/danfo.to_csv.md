---
description: Writes a DataFrame or Series to CSV format.
---

# danfo.to_csv

> danfo.**to_csv**(data, options) [\[source](https://github.com/opensource9ja/danfojs/blob/e25010c26d9c423412613d820015a48ad03d5c6d/danfojs-node/src/io/io.csv.js#L106)]

| **Parameters** | Type                | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | Default                                                                            |
| -------------- | ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| _**data**_     | Series or DataFrame | The Series or DataFrame to write to CSV                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                                                                                    |
| **options**    |  object, optional   | <p> Configuration object: </p><p>{</p><p> <strong><code>filePath</code></strong>: Local file path to write the CSV file to. If not specified, the CSV will be returned as a string. Only needed in Nodejs version<br><strong><code>fileName</code></strong>: The name of the file to download as. Only needed in browser environment. <br><strong><code>download</code></strong>: Boolean indicating whether to automatically download the CSV file in the browser. Only needed in the browser environment. </p><p><strong><code>header</code></strong>: Boolean indicating whether to include a header row in the CSV file.</p><p> <strong><code>sep</code></strong>: Character to be used as a separator in the CSV file.</p><p></p><p>}</p> | <p>{<br><strong>download</strong>: true,<br><strong>sep</strong>: ","<br><br>}</p> |

The **to_csv** function can be used to write out a DataFrame or Series to CSV file. The output is configurable and will depend on the environment. In the following examples, we show you how to write/download a CSV file from Node and Browser environments.

### Convert DataFrame to CSV string and return value

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

const csv = dfd.to_csv(df, { download: false });
console.log(csv);

//output
Abs,Count,country code
20.2,34,NG
30,4,FR
47.3,5,GH
```
{% endtab %}

{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.2/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>

    <script>

       let data = {
          Abs: [20.2, 30, 47.3],
          Count: [34, 4, 5],
          "country code": ["NG", "FR", "GH"],
        };
        
        let df = new dfd.DataFrame(data);
        
        const csv = df.to_csv({ download: false });
        console.log(csv);
    </script>
</body>

</html>

```
{% endtab %}
{% endtabs %}

### Convert DataFrame to CSV string and write to file path

Writing a CSV file to a local file path is only supported in the Nodejs environment

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

dfd.to_csv(df, { filePath: "testOut.csv"});
```
{% endtab %}
{% endtabs %}

### Convert DataFrame to CSV string and download file in Client-side lib

You can automatically convert and download a CSV file in a browser environment, by specifying a `fileName` and setting `download` to **true**. 

```javascript
const dfd = require("danfojs")

let data = {
    Abs: [20.2, 30, 47.3],
    Count: [34, 4, 5],
    "country code": ["NG", "FR", "GH"],
};

let df = new dfd.DataFrame(data);

dfd.to_csv(df, { fileName: "testOut.csv", download: true});
```
