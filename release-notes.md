# Release Notes

### \[LATEST\] Release [Danfojs-node \(v0.2.2\)](https://github.com/opensource9ja/danfojs/releases/tag/v0.2.2)

**Date:** 14th February 2021

We added/updated the following features:

* Fix runtime issue regarding @babel/runtime
* Smaller size in this version. From ~8mb to about ~5mb
* Fix browser tag issue and returns back to specific versioning instead of @latest
* Danfojs now ships with an exported version of tensorflowjs-node \(2.8.5\). This fixes the double dependency issue when building ML models, as you no longer need to install/import tensorflowjs separately.

To use tensoflowjs-node, you can reference it from danfo as shown below:

```javascript
const dfd = require("danfojs-node")
const tf = dfd.tf //contains a reference to the tensorflowjs-node library

const model = tf.sequential();
model.add(tf.layers.dense({ inputShape: [7], units: 124, activation: 'relu', kernelInitializer: 'leCunNormal' }));
model.add(tf.layers.dense({ units: 64, activation: 'relu' }));
model.summary();
```

### Release \(v0.1.5\)

**Date:** 25th September 2020

We added/updated the following features:

* [Read JSON](api-reference/input-output/danfo.read_json.md) files from local and remote URL into DataFrame \(New feature\)
* [Read Excel](api-reference/input-output/danfo.read_excel.md) files from local or remote URL into DataFrame \(New feature\)
* Fix string comparison bug in [query](api-reference/dataframe/danfo.dataframe.query.md) function \(Fix\)
* Add append function for [DataFrame](api-reference/dataframe/dataframe.append.md) and [Series](api-reference/series/series.append.md) \(New feature\)
* Fix null value bug when creating DataFrame from JSON files \(Fix\)
* Add relative import for reading files into DataFrame
* Add [sort\_index](api-reference/dataframe/dataframe.sort_index.md) function to DataFrame and Series \(New feature\)
* Minor patch and overall optimizations \(Fix\)

**Contributors**: [Rising Odegua](https://github.com/risenW), [Stephen Oni](https://github.com/steveoni), [Jhenner Tigreros](https://github.com/JhennerTigreros), [Aditya Zope](https://github.com/adzo261) 

### Release \(v0.1.0-beta\)

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



