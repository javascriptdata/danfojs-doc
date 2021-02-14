# Release Notes

### \[LATEST\] Release \(v0.1.5\)

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



