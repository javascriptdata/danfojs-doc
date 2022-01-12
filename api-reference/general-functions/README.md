---
description: Top level functions that can be called from the Danfo namespace
---

# General Functions

### Data transformation

|                                       |                                                                                                 |
| ------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [`merge`](danfo.merge.md)             | Merge DataFrame or named Series objects with a database-style join.                             |
| [`concat`](danfo.concat.md)           | Concatenate danfo objects along a particular axis with optional set logic along the other axes. |
| [`getDummies`](danfo.get\_dummies.md) | Convert categorical variable into dummy/indicator variables. Similar to OneHotEncoding          |

### Data Normalization

| [LabelEncoder](danfo.labelencoder.md)     | Encode target labels with value between 0 and n\_classes-1.            |
| ----------------------------------------- | ---------------------------------------------------------------------- |
| [OneHotEncoder](danfo.onehotencoder.md)   | Encode categorical features as a one-hot numeric array.                |
| [StandardScaler](danfo.standardscaler.md) | Standardize features by removing the mean and scaling to unit variance |
| [`MinMaxScaler`](danfo.minmaxscaler.md)   | Transform features by scaling each feature to a given range            |

### Working with DateTime

| [`toDateTime`](danfo.to\_datetime.md) | Convert argument to datetime.                                                                         |
| ------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| [`dateRange`](danfo.date\_range.md)   | Return a fixed frequency Datetime Index.                                                              |
|  [Dt](danfo.dt.md)                    | A class that converts strings of Date Time into a usable format, by exposing various helper methods.  |

### Streaming Functions

| [streamCSV](danfo.streamcsv.md)                                        | A function that loads a CSV object as a stream, returning intermediate rows as a DataFrame.              |
| ---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| [streamJSON](danfo.streamjson.md)                                      | A function that loads a JSON object as a stream, returning intermediate rows as a DataFrame.             |
| [streamCSVTransformer](danfo.streamcsvtransformer.md)                  | A function that loads a CSV object as a stream, and applies a map-reduce function to intermediate rows.  |
| [convertFunctionTotransformer](danfo.-convertfunctiontotransformer.md) | A function to convert any JS function into a Stream transformer.                                         |



### Utility and Configurations

| [Utils](danfo.utils.md)    | A utility class with helper methods mostly used internally.  |
| -------------------------- | ------------------------------------------------------------ |
| [Config](broken-reference) | Base configuration class for NDframe objects                 |

### Strings

| [Str](danfo.str.md) | A class that converts strings into a usable format, by exposing various helper methods. |
| ------------------- | --------------------------------------------------------------------------------------- |

### Internal Libs

| [tensoflow](danfo.tensorflow.md) | Exported Tensorflow.js library. This helps to avoid duplicated Tensorflow.js library use.  |
| -------------------------------- | ------------------------------------------------------------------------------------------ |

