---
description: >-
  The generic read function loads a tabular data using the Frictionless
  specification.
---

# read

> danfo.**read**\(source, configs\) [\[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/io/reader.js#L21)\]

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Parameters</b>
      </th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Default</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><em><b>source</b></em>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">A path to the file/resources. It can be a local file, a URL to tabular
        data (CSV, EXCEL) or Datahub.io Data Resource.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>configs</b>
      </td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">
        <p></p>
        <p>Configuration options. Supported params are:</p>
        <p><b>data_num</b> (Defaults =&gt; 0): The specific dataset to load, when
          reading data from a datapackage.json,</p>
        <p><b>header</b> (Defaults =&gt; true): Whether the dataset contains a header
          or not.</p>
        <p><b>sheet</b> (Defaults =&gt; 0): Number of the excel sheet which u want
          to load.</p>
        <p>}</p>
      </td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

**Returns:**

     ****_**Promise**_. Resolves to DataFrame

The **read** function uses [frictionless.js](https://github.com/frictionlessdata/frictionless-js) underhood.[`frictionless.js`](https://github.com/frictionlessdata/frictionless-js) is a lightweight, standardized "stream-plus-metadata" interface for accessing files and datasets, especially tabular ones \(CSV, Excel\). It follows the [Frictionless spec](https://frictionlessdata.io/specs/)

> ### **Note**: The `read` method is only available in danfojs-node at the moment.

### Read a CSV file

{% tabs %}
{% tab title="Node.js" %}
```javascript
const dfd = require("danfojs-node")

async function load_data() {
    let df = await dfd.read("file.csv")
    let sample = await df.sample(10)
    sample.print()
}

load_data()
```
{% endtab %}
{% endtabs %}

### **Loading Files from URL**

By specifying a valid URL, you can load CSV/EXCEL file:

{% tabs %}
{% tab title="Node.js" %}
```javascript
const dfd = require("danfojs-node")

async function load_data() {
 let df = await dfd.read("https://raw.githubusercontent.com/plotly/datasets/master/finance-charts-apple.csv")
 df.head().print()
}

load_data()
```
{% endtab %}
{% endtabs %}

### Loading Data from a Data Package Descriptor

You can load data from a frictionless data package [descriptor](https://specs.frictionlessdata.io/data-package/#descriptor). A data package descriptor is a central file in a Data Package. It is a JSON file that provides:

* General metadata such as the package’s title, license, publisher etc
* A list of the data “resources” that make up the package including their location on disk or online and other relevant information \(including, possibly, schema information about these data resources in a structured form\)

For instance, in the example below, we load the first resource in the [Natural Gas dataset](https://datahub.io/core/natural-gas) from datahub.io. 

{% tabs %}
{% tab title="JavaScript" %}
```javascript
const dfd = require("danfojs-node")

async function load_data() {
 const package_url =
    "https://datahub.io/core/natural-gas/datapackage.json";

  const df = await dfd.read(package_url, { data_num: 1 });
  df.head().print();

load_data()
```
{% endtab %}
{% endtabs %}

```bash
╔═══╤═══════════════════╤═══════════════════╗
║   │ Date              │ Price             ║
╟───┼───────────────────┼───────────────────╢
║ 0 │ 1997-01-07        │ 3.81999999999...  ║
╟───┼───────────────────┼───────────────────╢
║ 1 │ 1997-01-08        │ 3.79999999999...  ║
╟───┼───────────────────┼───────────────────╢
║ 2 │ 1997-01-09        │ 3.60999999999...  ║
╟───┼───────────────────┼───────────────────╢
║ 3 │ 1997-01-10        │ 3.91999999999...  ║
╟───┼───────────────────┼───────────────────╢
║ 4 │ 1997-01-13        │ 4                 ║
╚═══╧═══════════════════╧═══════════════════╝
```



