---
description: >-
  Danfo.js is an open-source, JavaScript library providing high-performance,
  intuitive, and easy-to-use data structures for manipulating and processing
  structured data.
---

# Danfo.js Documentation

D**anfo.js** is heavily inspired by the [Pandas](https://pandas.pydata.org/pandas-docs/stable/index.html) library and provides a similar interface and API. This means users familiar with the [Pandas ](https://pandas.pydata.org/pandas-docs/stable/index.html)API can easily use D**anfo.js.**&#x20;

## Main Features

* Danfo.js is fast and supports[ Tensorflow.js](https://js.tensorflow.org)'s tensors out of the box. This means you can [convert Danfo.js ](api-reference/dataframe/)DataFrames to Tensors, and vice versa.&#x20;
* Easy handling of missing **** data (represented as `NaN`) in floating point as well as non-floating point data
* Size mutability: columns can be inserted/deleted from DataFrame
* Automatic and explicit alignment: objects can be explicitly aligned to a set of labels, or the user can simply ignore the labels and let [`Series`](api-reference/series/), [`DataFrame`](api-reference/dataframe/), etc. automatically align the data for you in computations
* Powerful, flexible, [groupby](api-reference/groupby/) functionality to perform split-apply-combine operations on data sets, for both aggregating and transforming data
* Make it easy to convert Arrays, JSONs, List or Objects, Tensors, and differently-indexed data structures into DataFrame objects
* Intelligent label-based slicing, fancy indexing, and querying of large data sets
* Intuitive [merging](api-reference/general-functions/danfo.merge.md) and [joining](api-reference/general-functions/danfo.concat.md) data sets
* Robust IO tools for loading data from [flat-files](api-reference/input-output/danfo.read\_csv.md) (CSV and delimited), Excel, and JSON data format.
* Powerful, flexible, and intiutive API for [plotting](https://app.gitbook.com/@jsdata/s/danfojs/\~/drafts/-MESZnq3\_VBU0EW71MxS/api-reference/plotting) DataFrames and Series interactively.
* Timeseries-specific functionality: date range generation and date and time properties.
* Robust data preprocessing functions like [OneHotEncoders](api-reference/general-functions/danfo.onehotencoder.md), [LabelEncoders](api-reference/general-functions/danfo.labelencoder.md), and scalers like [StandardScaler](api-reference/general-functions/danfo.standardscaler.md) and [MinMaxScaler](api-reference/general-functions/danfo.minmaxscaler.md) are supported on DataFrame and Series

## Getting Started

New to Danfo? Check out the getting started guides. It contains a quick introduction to D_anfo's_ main concepts and links to additional content.

{% content-ref url="getting-started.md" %}
[getting-started.md](getting-started.md)
{% endcontent-ref %}

## **API Reference**

The reference guide contains a detailed description of the **danfo** API. The reference describes how each function works and which parameters can be used.&#x20;

{% content-ref url="api-reference/" %}
[api-reference](api-reference/)
{% endcontent-ref %}

## User Guides/Tutorials

{% content-ref url="examples/" %}
[examples](examples/)
{% endcontent-ref %}

## Building Data Driven Applications with Danfo.js - Book

{% content-ref url="building-data-driven-applications-with-danfo.js-book.md" %}
[building-data-driven-applications-with-danfo.js-book.md](building-data-driven-applications-with-danfo.js-book.md)
{% endcontent-ref %}

## Contributing Guide

Want to help improve our documentation and existing functionalities? The contributing guidelines will guide you through the process.&#x20;

{% content-ref url="contributing-guide.md" %}
[contributing-guide.md](contributing-guide.md)
{% endcontent-ref %}

## Release Notes

{% content-ref url="release-notes.md" %}
[release-notes.md](release-notes.md)
{% endcontent-ref %}

