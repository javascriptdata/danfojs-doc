---
description: Convert DataFrame to JSON format
---

# DataFrame.to\_json

danfo.DataFrame.**to\_json**\(path\) \[[source](https://github.com/opensource9ja/danfojs/blob/cf5c7ae3a009458e61eedd18d9c9b5b6b10d5276/danfojs/src/core/frame.js#L125)\]

**Returns:**

        ****returns **Promise**

## **Examples**

### Convert DataFrame to JSON format

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "Abs": [20.2, 30, 47.3] ,
             "Count": [34, 4, 5, 6] ,
             "country code": ["NG", "FR", "GH"] }


let df = new dfd.DataFrame(data)

df.to_json("/home/link/to/path.csv").then((json) => {
    console.log(json);
}).catch((err) => {
    console.log(err);
})
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
[{"Abs":20.2,"Count":34,"country code":"NG"},
{"Abs":30,"Count":4,"country code":"FR"},
{"Abs":47.3,"Count":5,"country code":"GH"}]
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
To export DataFrame as CSV, use [DataFrame.to\_csv](dataframe.to_json.md)
{% endhint %}

