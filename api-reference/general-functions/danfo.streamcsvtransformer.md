---
description: >-
  A pipeline transformer to stream a CSV file from local storage, transform it
  with a custom transformer, and write to the output stream. Only available in
  Node.js
---

# danfo.streamCsvTransformer

danfo.**streamCsvTransformer**(func)&#x20;

| Parameters    | Type     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ------------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| inputFilePath | Function | The path to the CSV file to stream from.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| transformer   | Function | <p>The transformer function to apply to each row. </p><p>Note that each row of the CSV file is passed as a DataFrame with a single row to the transformer function, and the transformer function is expected to return a transformed DataFrame.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| options       | object   | <p>Configuration options for the pipeline. These include:</p><ul><li><code>outputFilePath</code> The local file path to write the transformed CSV file to.</li><li><code>customCSVStreamWriter</code> A custom CSV stream writer function. This is applied at the end of each transform. If not provided, a default CSV stream writer is used, and this writes to local storage.</li></ul><ul><li><code>inputStreamOptions</code> Configuration options for the input stream. Supports all Papaparse CSV reader config options.</li><li><code>outputStreamOptions</code> Configuration options for the output stream. This is only applied when using the default CSV stream writer. Supports all <code>toCSV</code> options.</li></ul> |

**Returns:**

> return A promise that resolves when the pipeline transformation is complete.

The streamCsvTransformer can be used to [incrementally transform](https://en.wikipedia.org/wiki/Stream\_processing) a CSV file. This is done by:

* Streaming a CSV file from a local or **remote** path.
* Passing each corresponding row as a DataFrame to the specified transformer function.
* Writing the result to an output stream. &#x20;



## **Stream processing a local file**

In the example below, we stream a local CSV file (titanic.csv), applies a transformer function, and write the output to the `titanicOutLocal` file.

The transformer takes each `Name` column, splits the person's title, and creates a new column from it.&#x20;

{% tabs %}
{% tab title="Node" %}
```javascript
import { DataFrame, Series, streamCsvTransformer } from "danfojs-node";
import path from "path"

const inputFilePath = path.join(process.cwd(), "raw_data", "titanic.csv");
const outputFilePath = path.join(process.cwd(), "raw_data", "titanicOutLocal.csv");

/**
 * A simple function that takes a DataFrame, and transforms the Name column.
* */
const transformer = (df) => {
    const titles = df["Name"].map((name) => name.split(".")[0]);
    const names = df["Name"].map((name) => name.split(".")[1]);
    df["Name"] = names
    df.addColumn("titles", titles, { inplace: true })
    return df
}

dfd.streamCsvTransformer(inputFilePath, transformer, {
    outputFilePath,
    inputStreamOptions: { header: false }
})
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
//initial head of titanic.csv before transforming

PassengerId,Survived,Pclass,Name,Sex,Age,SibSp,Parch,Ticket,Fare,Cabin,Embarked
1,0,3,"Braund, Mr. Owen Harris",male,22,1,0,A/5 21171,7.25,,S
2,1,1,"Cumings, Mrs. John Bradley (Florence Briggs Thayer)",female,38,1,0,PC 17599,71.2833,C85,C
3,1,3,"Heikkinen, Miss. Laina",female,26,0,0,STON/O2. 3101282,7.925,,S


//Head of titanicOutLocal.csv after transforming

PassengerId,Survived,Pclass,Name,Sex,Age,SibSp,Parch,Ticket,Fare,Cabin,Embarked,titles
1,0,3, Owen Harris,male,22,1,0,A/5 21171,7.25,,S,Braund, Mr
2,1,1, John Bradley (Florence Briggs Thayer),female,38,1,0,PC 17599,71.2833,C85,C,Cumings, Mrs
3,1,3, Laina,female,26,0,0,STON/O2. 3101282,7.925,,S,Heikkinen, Miss
```
{% endtab %}
{% endtabs %}

## **Stream processing of remote file**

In the example below, we stream a remote CSV file (titanic.csv), applies a transformer function, and write the output to the `titanicOutLocal` file.

The transformer takes each `Name` column, splits the person's title, and creates a new column from it.&#x20;

{% tabs %}
{% tab title="Node" %}
```javascript
import { DataFrame, Series, streamCsvTransformer } from "danfojs-node";
import path from "path"

const inputFilePath = "https://raw.githubusercontent.com/opensource9ja/danfojs/dev/danfojs-node/tests/samples/titanic.csv"
const outputFilePath = path.join(process.cwd(), "raw_data", "titanicOutRemote.csv");


/**
 * A simple function that takes a DataFrame, and transforms the Name column.
* */
const transformer = (df) => {
    const titles = df["Name"].map((name) => name.split(".")[0]);
    const names = df["Name"].map((name) => name.split(".")[1]);
    df["Name"] = names
    df.addColumn("titles", titles, { inplace: true })
    return df
}

dfd.streamCsvTransformer(inputFilePath, transformer, {
    outputFilePath,
    inputStreamOptions: { header: false }
})
```
{% endtab %}
{% endtabs %}

## **Stream processing with a custom writer**

If you need custom control of the output writer, then you can provide a pipe-able custom writer. See [https://www.freecodecamp.org/news/node-js-streams-everything-you-need-to-know-c9141306be93/](https://www.freecodecamp.org/news/node-js-streams-everything-you-need-to-know-c9141306be93/)

In the example below, we add a custom writer that logs each row. You can extend this to upload each chunk to a database, or any other function you need.&#x20;

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require('danfojs-node-nightly')
const path = require("path")
const stream = require("stream")

const inputFilePath = "https://raw.githubusercontent.com/opensource9ja/danfojs/dev/danfojs-node/tests/samples/titanic.csv"

const transformer = (df) => {
    const titles = df["Name"].map((name) => name.split(".")[0]);
    const names = df["Name"].map((name) => name.split(".")[1]);
    df["Name"] = names
    df.addColumn("titles", titles, { inplace: true })
    return df
}
let count = 0

const customWriter = function () {
    const csvOutputStream = new stream.Writable({ objectMode: true })
    csvOutputStream._write = (chunk, encoding, callback) => {
        //Do anything here. For example you can write to online storage DB
        console.log("Chunk written: " + chunk) // Eah chunk is a row DataFrame
        count += 1
        callback()

    }
    return csvOutputStream
}

dfd.streamCsvTransformer(
    inputFilePath,
    transformer,
    {
        customCSVStreamWriter: customWriter,
        inputStreamOptions: { header: true }
    })
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
//Showing the last log
...

Chunk written: 
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ Survived          │ Pclass            │ Name              │ Sex               │ Age               │ Siblings/Spouse…  │ Parents/Childre…  │ Fare              │ titles            ║
╟────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 884        │ 0                 │ 3                 │  Patrick Dooley   │ male              │ 32                │ 0                 │ 0                 │ 7.75              │ Mr                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}
