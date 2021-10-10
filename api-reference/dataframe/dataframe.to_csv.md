---
description: Convert DataFrame data to a comma-separated values (csv)
---
# DataFrame.to_csv

danfo.DataFrame.**to_csv**(configs) \[[source](https://github.com/opensource9ja/danfojs/blob/cf5c7ae3a009458e61eedd18d9c9b5b6b10d5276/danfojs/src/core/frame.js#L125)]

****

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
