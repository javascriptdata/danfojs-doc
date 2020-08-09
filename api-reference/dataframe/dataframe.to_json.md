# DataFrame.to\_json

danfo.DataFrame.**to\_json**\(path\) \[[source](https://github.com/opensource9ja/danfojs/blob/cf5c7ae3a009458e61eedd18d9c9b5b6b10d5276/danfojs/src/core/frame.js#L125)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| **path** | String | Any valid file path |  |

**Returns:**

        ****returns **Promise**

              ****

## **Examples**

### Export DataFrame to JSON file path

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [{ "Abs": [20.2, 30, 47.3] },
            { "Count": [34, 4, 5, 6] },
            { "country code": ["NG", "FR", "GH"] }]


let df = new dfd.DataFrame(data)

df.to_json("/home/link/to/path.csv").then(()=>{
    console.log("Done");
    
}).catch((err)=>{

    console.log(err);
})
```
{% endtab %}
{% endtabs %}

> If a file path  not specified, return the Json file in string format

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [{ "Abs": [20.2, 30, 47.3] },
            { "Count": [34, 4, 5, 6] },
            { "country code": ["NG", "FR", "GH"] }]


let df = new dfd.DataFrame(data)

df.to_json().then((file)=>{

    console.log(file)
    
}).catch((err)=>{
    console.log(err)
})
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text

```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
To export DataFrame as CSV, use [DataFrame.to\_csv](dataframe.to_json.md)
{% endhint %}

