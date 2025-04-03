# danfo.toJSON

> danfo.toJSON(data, options)

|                |                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                 |
| -------------- | ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| **Parameters** | Type                | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Default                                                         |
| _**data**_     | Series or DataFrame | The Series or DataFrame to write to CSV                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                                                                 |
| **options**    | object, optional    | <p>Configuration object:</p><p>{</p><p><strong><code>filePath</code></strong>: Local file path to write the CSV file to. If not specified, the CSV will be returned as a string. Only needed in Nodejs version<br><strong><code>fileName</code></strong>: The name of the file to download as. Only needed in browser environment.<br><strong><code>format</code></strong>: The format of the JSON. Can be one of <strong><code>row</code></strong> or <strong><code>column</code></strong>.</p><p>}</p> | <p>{<br><strong><code>format</code></strong>: "column"<br>}</p> |

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

const jsonObj = dfd.toJSON(df); //column format
console.log(jsonObj);

//output
[
  { Abs: 20.2, Count: 34, 'country code': 'NG' },
  { Abs: 30, Count: 4, 'country code': 'FR' },
  { Abs: 47.3, Count: 5, 'country code': 'GH' }
]

//row format
const jsonObj = dfd.toJSON(df, {
    format: "row"
});

console.log(jsonObj);
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
     <script src="https://cdn.jsdelivr.net/npm/danfojs@1.2.0/lib/bundle.min.js"></script>
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
        
        const csv = df.toJSON();
        console.log(csv);
    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

### Convert DataFrame/Series to JSON and write to file path

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

dfd.toJSON(df, { filePath: "./testOutput.json" });
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

dfd.toJSON(df, { fileName: "test_out.json", download: true });
```
