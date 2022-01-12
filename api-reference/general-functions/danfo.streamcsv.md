---
description: >-
  Streams a CSV file from a local or remote location in chunks. Each
  intermediate chunk is passed as a DataFrame to the callback function.
---

# danfo.streamCSV

danfo.**streamCSV**(filePath, callback, options)&#x20;

| Parameters | Type     | Description                                                                                                    |
| ---------- | -------- | -------------------------------------------------------------------------------------------------------------- |
| filePath   | string   | URL or local file path to CSV file.                                                                            |
| callback   | Function | Callback function to be called once the specifed rows are parsed into DataFrame.                               |
| options    | object   | Optional configuration object. Supports all [Papaparse](https://www.papaparse.com/docs#config) config options. |

The **streamCSV** function streams a CSV file from a local or remote location in chunks. Each intermediate chunk is passed as a DataFrame to the callback function.

## **Stream CSV file from local path**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")
const path = require("path")

const filePath = path.join(process.cwd(), "raw_data", "titanic.csv");

dfd.streamCSV(filePath, (df) => {
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
//Showing few rows 
...

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ PassengerId       │ Survived          │ Pclass            │ Name              │ ...               │ Fare              │ Cabin             │ Embarked          ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 676        │ 687               │ 0                 │ 3                 │ Panula, Mr. Jaa…  │ ...               │ 39.6875           │                   │ S                 ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ PassengerId       │ Survived          │ Pclass            │ Name              │ ...               │ Fare              │ Cabin             │ Embarked          ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 677        │ 688               │ 0                 │ 3                 │ Dakic, Mr. Bran…  │ ...               │ 10.1708           │                   │ S                 ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

...
```
{% endtab %}
{% endtabs %}

## **Stream CSV file from remote path**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

const remoteFile = "https://raw.githubusercontent.com/opensource9ja/danfojs/dev/danfojs-node/tests/samples/titanic.csv"

const callback = (df) => {
    //Perform any processing here
    if (df) {
        df.print();
    }
}

dfd.streamCSV(remoteFile, callback, { header: true })
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
//Showing a few rows 
...

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ Survived          │ Pclass            │ Name              │ Sex               │ Age               │ Siblings/Spouse…  │ Parents/Childre…  │ Fare              ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 523        │ 0                 │ 1                 │ Mr. John Farthi…  │ male              │ 49                │ 0                 │ 0                 │ 221.7792          ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ Survived          │ Pclass            │ Name              │ Sex               │ Age               │ Siblings/Spouse…  │ Parents/Childre…  │ Fare              ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 524        │ 0                 │ 3                 │ Mr. Johan Werne…  │ male              │ 39                │ 0                 │ 0                 │ 7.925             ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

...
```
{% endtab %}
{% endtabs %}
