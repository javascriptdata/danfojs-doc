---
description: >-
  Streams a JSON file from a  local or remote location in chunks. Each
  intermediate chunk is passed as a DataFrame to the callback function.
---

# danfo.streamJSON

danfo.**streamJSON**(filePath, callback, options)&#x20;

| Parameters | Type     | Description                                                                                                                                                           |
| ---------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| filePath   | string   | URL or local file path to CSV file.                                                                                                                                   |
| callback   | Function | Callback function to be called once the specifed rows are parsed into DataFrame.                                                                                      |
| options    | object   | Optional configuration object. We use the `request` library for reading remote json files, Hence all `request` parameters such as `method`, `headers`, are supported. |

The **streamJSON** function streams a JSON file from a local or remote location in chunks. Each intermediate chunk is passed as a DataFrame to the callback function.

## **Stream JSON file from local path**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
const path = require("path")

const filePath = path.join(process.cwd(), "raw_data", "book_small.json");

dfd.streamJSON(filePath, (df) => {
    if (df) {
        // Do any processing here
        df.print();
    }
});
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
//Showing the last rows 
...

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ book_id           │ title             │ image_url         │ authors           ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 10         │ 32848471          │ Egomaniac         │ https://images.…  │ Vi Keeland        ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ book_id           │ title             │ image_url         │ authors           ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 11         │ 33288638          │ Wait for It       │ https://s.gr-as…  │ Mariana Zapata    ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

## **Stream JSON file from remote path**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
const path = require("path")

const remoteFile = "https://raw.githubusercontent.com/opensource9ja/danfojs/dev/danfojs-node/tests/samples/book.json"

const callback = (df) => {
    //Perform any processing here
    if (df) {
        df.print();
    }
}

dfd.streamJSON(remoteFile, callback, { header: true })
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
//Showing a few rows 
...

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ book_id           │ title             │ image_url         │ authors           ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 10         │ 32848471          │ Egomaniac         │ https://images.…  │ Vi Keeland        ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ book_id           │ title             │ image_url         │ authors           ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 11         │ 33288638          │ Wait for It       │ https://s.gr-as…  │ Mariana Zapata    ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
