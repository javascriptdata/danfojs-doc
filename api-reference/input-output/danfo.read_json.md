---
description: Reads a JSON file into DataFrame.
---

# danfo.read\_json

> danfo.**read\_json**\(source,\) [\[source](https://github.com/opensource9ja/danfojs/blob/849d14c8e7fa79bce4ffa9d0d177639047313520/danfojs/src/io/reader.js#L47)\]

| **Parameters** | Type | Description |
| :--- | :--- | :--- |
| _**source**_: | **string**, path or URL  | Any valid string path is acceptable. The string could be a URL. Valid URL schemes include http, https, ftp, s3, gs, or a local path. Both relative and absolute paths are supported |

**Returns:**

     ****_**Promise**_. Resolves to DataFrame

### Example

The **read\_json** method can read JSON file from local disk, or over the internet. For instance, in the example below, user\_names.json is a JSON file in this same directory as our script. To read it into danfo DataFrame, you can specify the relative path:

{% tabs %}
{% tab title="Node.js" %}
```javascript
const dfd = require("danfojs-node")

dfd.read_json("user_names.json")
  .then(df => {
  
   df.head().print()

  }).catch(err=>{
     console.log(err);
  })
```
{% endtab %}

{% tab title="Browser" %}
```markup

```
{% endtab %}
{% endtabs %}

