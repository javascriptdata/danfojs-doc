---
description: Convert DataFrame data to a comma-separated values (csv)
---
# DataFrame.to_csv

DataFrame.**to_csv**(options) \[[source](https://github.com/opensource9ja/danfojs/blob/cf5c7ae3a009458e61eedd18d9c9b5b6b10d5276/danfojs/src/core/frame.js#L125)]

| **Parameters** | Type              | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | Default                                                                            |
| -------------- | ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| **options**    |  object, optional | <p> Configuration object: </p><p>{</p><p> <strong><code>filePath</code></strong>: Local file path to write the CSV file to. If not specified, the CSV will be returned as a string. Only needed in Nodejs version<br><strong><code>fileName</code></strong>: The name of the file to download as. Only needed in browser environment. <br><strong><code>download</code></strong>: Boolean indicating whether to automatically download the CSV file in the browser. Only needed in the browser environment. </p><p><strong><code>header</code></strong>: Boolean indicating whether to include a header row in the CSV file.</p><p> <strong><code>sep</code></strong>: Character to be used as a separator in the CSV file.</p><p></p><p>}</p> | <p>{<br><strong>download</strong>: true,<br><strong>sep</strong>: ","<br><br>}</p> |

The **to_csv** function can be used to write out a DataFrame or Series to CSV file. The output is configurable and will depend on the environment. In the following examples, we show you how to write/download a CSV file from Node and Browser environments.

## **Examples**

### Convert DataFrame to CSV format

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Abs": [20.2, 30, 47.3] ,
             "Count": [34, 4, 5, 6] ,
             "country code": ["NG", "FR", "GH"] }


let df = new dfd.DataFrame(data)

df.to_csv("/home/link/to/path.csv").then((csv) => {
    console.log(csv);

}).catch((err) => {

    console.log(err);
})
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
Abs,Count,country code
20.2,34,NG
30,4,FR
47.3,5,GH
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
To export DataFrame as Json, use [DataFrame.to_json](dataframe.to_json.md)
{% endhint %}
