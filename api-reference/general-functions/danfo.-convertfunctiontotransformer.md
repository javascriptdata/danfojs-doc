---
description: Converts a function to a pipe transformer. Only available in Nodejs version.
---

# danfo. convertFunctionTotransformer

danfo.**convertFunctionTotransformer**(func)&#x20;

| Parameters | Type     | Description                                                                                                                         | Default |
| ---------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------- | ------- |
| **func**   | Function | A valid JavaScript function to convert to a [pipe transformer.](https://nodejs.org/api/stream.html#implementing-a-transform-stream) |         |

**Returns:**

> return A [pipe transformer](https://nodejs.org/api/stream.html#implementing-a-transform-stream) that applies the function to each row of object.

The **convertFunctionTotransformer** takes a function and converts it to a Nodejs stream transformer function which can be used in combination with streamCsvTransformer to incrementally transform large files.&#x20;

## **Converting a function to a transformer**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

/*
 * A simple function that takes each row of a DataFrame and splits the
 * name field. 
*/
const renamer = (dfRow: DataFrame) => {
    const dfModified = dfRow["Names"].map((name) => name.split(",")[0])
    return dfModified
}

const transformer = dfd.convertFunctionTotransformer(renamer)
console.log(transformer)
```
{% endtab %}

{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <!--danfojs CDN -->
    <script src="https://cdn.jsdelivr.net/gh/opensource9ja/danfojs@latest/lib/bundle.js"></script>
    <title>Document</title>
</head>

<body>

    <script>

        let data = new dfd.date_range({"start":'1/1/2018',period:5, freq:'M'})
        console.log(data);
         
    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
Transform {
  _readableState: ReadableState {
    objectMode: true,
    highWaterMark: 16,
    buffer: BufferList { head: null, tail: null, length: 0 },
    length: 0,
    pipes: [],
    flowing: null,
    ended: false,
    endEmitted: false,
    reading: false,
    sync: false,
    needReadable: false,
    emittedReadable: false,
    readableListening: false,
    resumeScheduled: false,
    errorEmitted: false,
    emitClose: true,
    autoDestroy: true,
    destroyed: false,
    errored: null,
    closed: false,
    closeEmitted: false,
    defaultEncoding: 'utf8',
    awaitDrainWriters: null,
    writecb: null,
    writechunk: null,
    writeencoding: null
  }
}
```
{% endtab %}
{% endtabs %}
