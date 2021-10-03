---
description: >-
  Reads a comma-separated values (CSV) file into DataFrame. Also supports the
  reading of CSV files in chunks.
---

# danfo.read\_csv

> danfo.**read\_csv**\(source, configs\) [\[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/io/reader.js#L21)\]

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
      <td style="text-align:left"><em><b>source</b></em>:</td>
      <td style="text-align:left">str, path or URL</td>
      <td style="text-align:left">Any valid string path is acceptable. The string could be a URL. Valid
        URL schemes include https, http, ftp, s3, gs, and file. Local file paths
        are only accepted in Nodejs environment.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>configs</b>:</td>
      <td style="text-align:left">object, optional</td>
      <td style="text-align:left">
        <p></p>
        <p>A CSV Config object that contains configurations for reading and decoding
          from CSV file(s). Supported params are:</p>
        <p><b>start</b>: The index position to start from when reading the CSV file.</p>
        <p><b>end</b>: The end position to stop at when reading the CSV file.</p>
        <p><b>... csvConfigs</b>: other supported Tensorflow csvConfig parameters.
          See <a href="https://js.tensorflow.org/api/latest/#data.csv">https://js.tensorflow.org/api/latest/#data.csv</a> 
        </p>
      </td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

**Returns:**

     ****_**Promise**_. Resolves to DataFrame

### Example

The **read\_csv** method can read a csv file from local disk, or over the internet \(URL\). Reading of local files are only supported in danfojs-node. 

{% tabs %}
{% tab title="Node.js" %}
```javascript
const dfd = require("danfojs-node")

dfd.read_csv("user_names.csv") //assumes file is in CWD
  .then(df => {
  
   df.head().print()

  }).catch(err=>{
     console.log(err);
  })
```
{% endtab %}

{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.plot.ly/plotly-1.2.0.min.js"></script> 
     <script src="https://cdn.jsdelivr.net/npm/danfojs@0.2.4/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

         dfd.read_csv("https://raw.githubusercontent.com/plotly/datasets/master/finance-charts-apple.csv")
            .then(df => {

                //do something like display descriptive statistics
                df.describe().print()
                
            }).catch(err => {
                console.log(err);
            })
         
    </script>
</body>

</html>

```
{% endtab %}
{% endtabs %}

**Loading Files from URL**

By specifying a valid URL, you can load CSV files from any location into Danfo**'**s data structure:

{% tabs %}
{% tab title="Node.js" %}
```javascript
const dfd = require("danfojs-node")

dfd.read_csv("https://raw.githubusercontent.com/plotly/datasets/master/finance-charts-apple.csv") //assumes file is in CWD
  .then(df => {
  
   df.head().print()

  }).catch(err=>{
     console.log(err);
  })
```
{% endtab %}

{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.plot.ly/plotly-1.2.0.min.js"></script> 
     <script src="https://cdn.jsdelivr.net/npm/danfojs@0.2.4/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

         dfd.read_csv("https://raw.githubusercontent.com/plotly/datasets/master/finance-charts-apple.csv")
            .then(df => {

                //do something like display descriptive statistics
                df.describe().print()
                
            }).catch(err => {
                console.log(err);
            })
         
    </script>
</body>

</html>

```
{% endtab %}
{% endtabs %}

**Reading Large Files**

For extremely large files, that cannot be fit in memory at once, you can load them in chunks. For instance, this [dataset](http://eforexcel.com/wp/wp-content/uploads/2017/07/1500000%20Sales%20Records.7z) has over 1.5 million rows and will throw a memory error if you try to load everything at once. To read these type of files, you can load them in chunks and perform preprocessing to each chunk:

**Note**: The dataset used in the following example cannot be downloaded over the internet as it is a zip file. So we download locally, unzip and load it in a danfojs-node environment.

{% tabs %}
{% tab title="JavaScript" %}
```javascript
const dfd = require("danfojs-node")

async function load_process_data() {
  let df_chunk1 = await dfd.read_csv("1500000 Sales Records.csv", {start: 0, end: 10})
  let df_chunk2 = await dfd.read_csv("1500000 Sales Records.csv", {start: 10, end: 20})

  df_chunk1.head().print()
  df_chunk2.head().print()
}

load_process_data()
```
{% endtab %}

{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.jsdelivr.net/npm/danfojs@0.2.4/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>


        async function run(start, end) {
            let data_url = "https://raw.githubusercontent.com/plotly/datasets/master/finance-charts-apple.csv"
            let df = await dfd.read_csv(data_url, { start, end })
            console.log(df.shape)
            df.head().print()
        }

        run(0, 5)
        run(5, 10)

    </script>
</body>

</html>

<!
Output in console

[5, 11]
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Date              │ AAPL.Open         │ AAPL.High         │ AAPL.Low          │ ...               │ dn                │ mavg              │ up                │ direction         ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 2015-02-17        │ 127.489998        │ 128.880005        │ 126.919998        │ ...               │ 106.7410523       │ 117.9276669       │ 129.1142814       │ Increasing        ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 2015-02-18        │ 127.629997        │ 128.779999        │ 127.449997        │ ...               │ 107.842423        │ 118.9403335       │ 130.0382439       │ Increasing        ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2015-02-19        │ 128.479996        │ 129.029999        │ 128.330002        │ ...               │ 108.8942449       │ 119.8891668       │ 130.8840887       │ Decreasing        ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 2015-02-20        │ 128.619995        │ 129.5             │ 128.050003        │ ...               │ 109.7854494       │ 120.7635001       │ 131.7415509       │ Increasing        ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ 2015-02-23        │ 130.020004        │ 133               │ 129.660004        │ ...               │ 110.3725162       │ 121.7201668       │ 133.0678174       │ Increasing        ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

[10, 11]
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Date              │ AAPL.Open         │ AAPL.High         │ AAPL.Low          │ ...               │ dn                │ mavg              │ up                │ direction         ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 2015-02-24        │ 132.940002        │ 133.600006        │ 131.169998        │ ...               │ 111.0948689       │ 122.6648335       │ 134.2347981       │ Decreasing        ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 2015-02-25        │ 131.559998        │ 131.600006        │ 128.149994        │ ...               │ 113.2119183       │ 123.6296667       │ 134.0474151       │ Decreasing        ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 2015-02-26        │ 128.789993        │ 130.869995        │ 126.610001        │ ...               │ 114.1652991       │ 124.2823333       │ 134.3993674       │ Increasing        ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 2015-02-27        │ 130               │ 130.570007        │ 128.240005        │ ...               │ 114.9668484       │ 124.8426669       │ 134.7184854       │ Decreasing        ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ 2015-03-02        │ 129.25            │ 130.279999        │ 128.300003        │ ...               │ 115.8770904       │ 125.4036668       │ 134.9302432       │ Decreasing        ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝


>

```
{% endtab %}
{% endtabs %}

```bash
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Region            │ Country           │ Item Type         │ Sales Channel     │ ...               │ Unit Cost         │ Total Revenue     │ Total Cost        │ Total Profit      ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ Sub-Saharan A...  │ South Africa      │ Fruits            │ Offline           │ ...               │ 6.92              │ 14862.69          │ 11023.56          │ 3839.13           ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Middle East a...  │ Morocco           │ Clothes           │ Online            │ ...               │ 35.84             │ 503890.08         │ 165258.24         │ 338631.84         ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ Australia and...  │ Papua New Guinea  │ Meat              │ Offline           │ ...               │ 364.69            │ 151880.4          │ 131288.4          │ 20592             ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ Sub-Saharan A...  │ Djibouti          │ Clothes           │ Offline           │ ...               │ 35.84             │ 61415.36          │ 20142.08          │ 41273.28          ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ Europe            │ Slovakia          │ Beverages         │ Offline           │ ...               │ 31.79             │ 188518.85         │ 126301.67         │ 62217.18          ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Region            │ Country           │ Item Type         │ Sales Channel     │ ...               │ Unit Cost         │ Total Revenue     │ Total Cost        │ Total Profit      ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ Asia              │ Taiwan            │ Fruits            │ Offline           │ ...               │ 6.92              │ 74957.22          │ 55595.28          │ 19361.94          ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ Middle East a...  │ Algeria           │ Cosmetics         │ Online            │ ...               │ 263.33            │ 4227286.8         │ 2546137.77        │ 1681149.03        ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ Asia              │ Singapore         │ Snacks            │ Online            │ ...               │ 97.44             │ 1171204.08        │ 747949.44         │ 423254.64         ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ Australia and...  │ Papua New Guinea  │ Clothes           │ Offline           │ ...               │ 35.84             │ 993573.76         │ 325857.28         │ 667716.48         ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ Asia              │ Vietnam           │ Personal Care     │ Online            │ ...               │ 56.67             │ 652532.32         │ 452453.28         │ 200079.04         ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```



