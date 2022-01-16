# Release Notes

### \[LATEST] Release Node (v1.0.1), Browser (v1.0.1)

**Date:** 16th Jan 2022

Minor bug fixes

* [https://github.com/javascriptdata/danfojs/issues/354](https://github.com/javascriptdata/danfojs/issues/354)
* [https://github.com/javascriptdata/danfojs/issues/344](https://github.com/javascriptdata/danfojs/issues/344)
* [https://github.com/javascriptdata/danfojs/pull/347](https://github.com/javascriptdata/danfojs/pull/347)

Contributors: @[**Devwulf**](https://github.com/Devwulf)**,** [@risenW](https://github.com/risenW)

### Release Node (v1.0.0), Browser (v1.0.0)

**Date:** 12th Jan 2022

Major breaking update. See the migration [guide](examples/migrating-to-the-stable-version-of-danfo.js.md) for pre-v1 users.

**New Features**

* Full Typescript support
* streamCsvTransforme ==> Pipable stream transformer for incrementally transforming DataFrames
* streamJSON ==> Supports streaming of local or remote JSON files into DataFrame.
* streamCSV ==> Supports streaming of local or remote CSV files into DataFrame.
* openCsvInputStream ==> Open a local/remote CSV file as a readable stream
* writeCsvOutputStream ==> Open a local/remote CSV file as a writable stream
* [https://github.com/javascriptdata/danfojs/issues/325](https://github.com/javascriptdata/danfojs/issues/325)
* [https://github.com/javascriptdata/danfojs/issues/296](https://github.com/javascriptdata/danfojs/issues/296)

**Bug Fixes**

* [https://github.com/javascriptdata/danfojs/issues/335](https://github.com/javascriptdata/danfojs/issues/335)
* [https://github.com/javascriptdata/danfojs/issues/338](https://github.com/javascriptdata/danfojs/issues/338)

Contributors [@risenW](https://github.com/risenW) [@steveoni](https://github.com/steveoni)

### Release Node (v0.3.3), Browser (0.3.3)

**Date:** 10th Oct 2021

Minor patch update

### Release - Node (v0.3.2), Browser (0.3.2)

**Date:** 2nd Oct 2021

Minor patch update for column name display after aggregation functions like sum, mean, var, are applied to a column axis.

### Release - Node (v0.3.1), Browser (0.3.1)

**Date:** 1st Oct 2021

**New Features**

* Ability to create empty frames
* Flag for toggling between low/high memory mode
* Inplace support for all mutating operations
* Ability to set Configuration values on frame creation
* Support boolean mask for subsetting with `iloc` and `loc`. E.g `df.iloc({rows: df["count"].gt(5), columns: [0, 1]})`
* Update an existing column value via subsetting. E.g `df["count"] = [1,3,4,5]`
* Add loc indexing support for Series
* Add configuration support for formating DataFrame display in the console
* New DataFrame `applyMap` function for element-wise apply function
* `and` and `or` logical comparison support. E.g\
  `df.loc({`\
  `rows: df['Salary_in_1000'].gte(100)).and(df['Age'].gt(60))`\
  `})`
* `read_csv` now uses [Papaparse](https://www.papaparse.com) and supports config values for headers, separator, etc.
* `to_csv` , `to_json` and `to_excel` functions now support saving to local disk in Node and downloadable in the browser. Also, supports config parameters for output.
* `read_json` now supports config values for headers, authentication, separator, etc.
* `read_excel` now uses [XLSX](https://www.npmjs.com/package/xlsx) parser, hence supports all XLSX config options.
* DataFrame `query` function now accepts boolean masks with single or multiple conditions. E.g\
  `df.query({`\
  `rows: df['Salary_in_1000'].gte(100)).and(df['Age'].gt(60))`\
  `})`

**Bug Fixes**

* Column data not being updated when mutating internal data array
* Str class error for non-string type
* Better error message
* Fix support for all JS Date format
* Fix loc slicing bug for row index with string labels
* DataFrame apply function now works only across a specified axis

Contributors [@risenW](https://github.com/risenW)

### \[LATEST] ReleaseNode (v0.2.7), Browser (0.2.6)

**Date:** 30th May 2021

\[Bug Fixes]: [#206](https://github.com/opensource9ja/danfojs/issues/206) [#203](https://github.com/opensource9ja/danfojs/issues/203) [#200](https://github.com/opensource9ja/danfojs/issues/200) [#198](https://github.com/opensource9ja/danfojs/issues/198) [#198](https://github.com/opensource9ja/danfojs/issues/198) [#188](https://github.com/opensource9ja/danfojs/issues/188) [#181](https://github.com/opensource9ja/danfojs/issues/181) [#175](https://github.com/opensource9ja/danfojs/issues/175) [#183](https://github.com/opensource9ja/danfojs/issues/183) [#168](https://github.com/opensource9ja/danfojs/issues/168)\
\[Patches] [#191](https://github.com/opensource9ja/danfojs/issues/191) [#161](https://github.com/opensource9ja/danfojs/issues/161) [#206](https://github.com/opensource9ja/danfojs/issues/206)

Contributors [@risenW](https://github.com/risenW) [@steveoni](https://github.com/steveoni) [@jpjagt](https://github.com/jpjagt) [@sponsfreixes](https://github.com/sponsfreixes) [@bherbruck](https://github.com/bherbruck) [@woosuk288](https://github.com/woosuk288) and [@adithyaakrishna](https://github.com/adithyaakrishna)

### ReleaseNode (v0.2.6), Browser (0.2.5)

**Date:** 29th March 2021

* \[Bug Fixes]: [#150](https://github.com/opensource9ja/danfojs/pull/150) [#152](https://github.com/opensource9ja/danfojs/pull/152)
* \[Patches] [#159](https://github.com/opensource9ja/danfojs/pull/159) , [#158](https://github.com/opensource9ja/danfojs/pull/158)
* \[Feature] [#154](https://github.com/opensource9ja/danfojs/pull/154) Perform groupby operation on grouped columns directly:

```javascript
group = df.groupby(['A"])
group.min()


groupby.apply((x) => x.add(2))
groupby.col(["C"]).apply((x) => x.min())
```

**Contributors**: @steveoni @PrawiraGenestonlia @woosuk288 @risenW

### Release Node (v0.2.5), Browser (0.2.4)

**Date:** 6th March 2021

We added/updated the following features:

* Fix error thrown when danfojs CDN is placed in an HTML header
* Smaller bundle size for browser: From \~1.7mb to about \~550kb
* Stopped bundling Danfojs with Plotly. This means that as of v0.2.3, we no longer ship with Plotly distribution due to the huge size. Plotly plots are still supported, but in order to make them, you have to explicitly add the Plotly CDN or package.

A simple example:

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.plot.ly/plotly-1.2.0.min.js"></script> 
    <script src="https://cdn.jsdelivr.net/npm/danfojs@1.0.1/lib/bundle.js"></script> 

    <title>Document</title>
</head>

<body>

    <div id="div1"></div>
    <div id="div2"></div>
    <div id="div3"></div>

    <script>

        dfd.read_csv("https://raw.githubusercontent.com/plotly/datasets/master/finance-charts-apple.csv")
            .then(df => {

                df['AAPL.Open'].plot("div1").box() //makes a box plot

                df.plot("div2").table() //display csv as table

                new_df = df.set_index({ key: "Date" }) //resets the index to Date column
                new_df.plot("div3").line({ columns: ["AAPL.Open", "AAPL.High"] })  //makes a timeseries plot

            }).catch(err => {
                console.log(err);
            })

    </script>
    
</body>

</html>
```

### Release [(v0.2.2)](https://github.com/opensource9ja/danfojs/releases/tag/v0.2.2)

**Date:** 14th February 2021

We added/updated the following features:

* Fix babel runtime issue in node version
* Smaller size in browser version in this version. From \~8mb to about \~5mb
* Fix browser tag issue and returns back to specific versioning instead of @latest
* Danfojs now ships with an exported version of tensorflowjs-node (2.8.5). This fixes the double dependency issue when building ML models, as you no longer need to install/import tensorflowjs separately.

To use tensoflowjs-node, you can reference it from danfo as shown below:

```javascript
const dfd = require("danfojs-node")
const tf = dfd.tf //contains a reference to the tensorflowjs-node library

const model = tf.sequential();
model.add(tf.layers.dense({ inputShape: [7], units: 124, activation: 'relu', kernelInitializer: 'leCunNormal' }));
model.add(tf.layers.dense({ units: 64, activation: 'relu' }));
model.summary();
```

### Release (v0.1.5)

**Date:** 25th September 2020

We added/updated the following features:

* [Read JSON](api-reference/input-output/danfo.read\_json.md) files from local and remote URL into DataFrame (New feature)
* [Read Excel](api-reference/input-output/danfo.read\_excel.md) files from local or remote URL into DataFrame (New feature)
* Fix string comparison bug in [query](api-reference/dataframe/danfo.dataframe.query.md) function (Fix)
* Add append function for [DataFrame](api-reference/dataframe/dataframe.append.md) and [Series](api-reference/series/series.append.md) (New feature)
* Fix null value bug when creating DataFrame from JSON files (Fix)
* Add relative import for reading files into DataFrame
* Add [sort\_index](api-reference/dataframe/dataframe.sort\_index.md) function to DataFrame and Series (New feature)
* Minor patch and overall optimizations (Fix)

**Contributors**: [Rising Odegua](https://github.com/risenW), [Stephen Oni](https://github.com/steveoni), [Jhenner Tigreros](https://github.com/JhennerTigreros), [Aditya Zope](https://github.com/adzo261)

### Release (v0.1.0-beta)

**Date:** 15th August 2020

This is a minor release for browser-based environments. We added/updated the following features:

* Ability to create DataFrame/Series from Tensors
* Add iloc function for Series
* Update [addColumns](api-reference/dataframe/danfo.dataframe.addcolumn.md) function to accept Series
* Add inplace option for [fillna](api-reference/dataframe/danfo.dataframe.fillna.md)
* Fix bug in [rename](api-reference/dataframe/dataframe.rename.md) function of DataFrame
* Add Inplace option for [query](api-reference/dataframe/danfo.dataframe.query.md)
* Fixed upper bound bug in indexing

**Contributors**: Rising Odegua, Stephen Oni
