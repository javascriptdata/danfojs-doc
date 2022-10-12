---
description: Convert DataFrame to JSON format
---

# DataFrame.toJSON

{% hint style="danger" %}
Deprecated in v1.1.0: Use the [dfd.toJSON](../input-output/danfo.to\_json.md) function directly instead
{% endhint %}

> DataFrame.toJSON(options)

|                |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                                                                 |
| -------------- | ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------- |
| **Parameters** | Type             | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | Default                                                         |
| **options**    | object, optional | <p>Configuration object:</p><p><strong><code>filePath</code></strong>: Local file path to write the CSV file to. If not specified, the CSV will be returned as a string. Only needed in Nodejs version</p><p><br><strong><code>fileName</code></strong>: The name of the file to download as. Only needed in browser environment.</p><p><br><strong><code>format</code></strong>: The format of the JSON. Can be one of <strong><code>row</code></strong> or <strong><code>column</code></strong>.</p> | <p>{<br><strong><code>format</code></strong>: "column"<br>}</p> |

The **toJSON** function can be used to write out a DataFrame or Series to JSON format/file. The output is configurable and will depend on the environment. In the following examples, we show you how to write/download a JSON file from Node and Browser environments.

### Convert DataFrame/Series to JSON and return value

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

const jsonObj = df.toJSON(); //defaults to column format
console.log(jsonObj);

//output
[
  { Abs: 20.2, Count: 34, 'country code': 'NG' },
  { Abs: 30, Count: 4, 'country code': 'FR' },
  { Abs: 47.3, Count: 5, 'country code': 'GH' }
]

//row format
const jsonObjRow = df.toJSON({
    format: "row"
});
  

console.log(jsonObjRow);
//output
{
  Abs: [ 20.2, 30, 47.3 ],
  Count: [ 34, 4, 5 ],
  'country code': [ 'NG', 'FR', 'GH' ]
}
```
{% endtab %}

{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <script src="https://cdn.jsdelivr.net/npm/danfojs@1.1.2/lib/bundle.min.js"></script>
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

### Convert DataFrame/Series to JSON and write to local file path

Writing a DataFrame/Series as JSON, to a local file path is only supported in the Nodejs environment

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

df.toJSON({ filePath: "./testOutput.json" });
```
{% endtab %}
{% endtabs %}

### Convert DataFrame/Series to JSON and download file in browser

You can automatically convert and download a DataFrame/Series as a JSON file in a browser environment, by specifying a `fileName` and setting `download` to **true**.

```javascript
let data = {
    Abs: [20.2, 30, 47.3],
    Count: [34, 4, 5],
    "country code": ["NG", "FR", "GH"],
};

let df = new dfd.DataFrame(data);

df.toJSON({ fileName: "test_out.json", download: true });
```
