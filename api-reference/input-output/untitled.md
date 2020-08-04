---
description: Reads a JSON file from local or remote address
---

# danfo.read\_json

> danfo.**read\_json**\(source, chunk\) [\[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/io/reader.js#L38)\]

| **Parameters** | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| _**source**_ | str, path or URL  | Any valid string path is acceptable. The string could be a URL or a local file path. Valid URL schemes include http, ftp, s3, gs, and file.  |  |

**Returns:**

     ****_**Promise**_. Resolves to DataFrame

### Example

The **read\_json** method can read a JSON file from local disk, or over the internet. For browser based environment, ensure to serve the file path from a server. 

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")


const jsonUrl = "https://somefile.json"

dfd.read_json(jsonUrl)
    .then(df => {
        df.head().print()

    }).catch(err ={
        console.log(err)
    })
    
    
    
    
const localJson = "/path-to-local-file.json"

dfd.read_json(localJson)
    .then(df => {
        df.tail().print()

    }).catch(err ={
        console.log(err)
    })
```
{% endtab %}

{% tab title="Browser" %}
```

```
{% endtab %}
{% endtabs %}

