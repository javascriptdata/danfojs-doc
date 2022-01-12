---
description: Two-dimensional, size-mutable, potentially heterogeneous tabular data.
---

# Dataframe

### Attributes

| [`DataFrame.index`](dataframe.index.md)          | The index (row labels) of the DataFrame. |
| ------------------------------------------------ | ---------------------------------------- |
| [`DataFrame.columns`](danfo.dataframe.column.md) | The column labels of the DataFrame.      |

| [`DataFrame.ctypes`](dataframe.dtypes.md) |   |
| ----------------------------------------- | - |
| [`DataFrame.values`](dataframe.values.md) |   |
| [`DataFrame.axis`](dataframe.axes.md)     |   |
| [`DataFrame.ndim`](dataframe.ndim.md)     |   |
| [`DataFrame.size`](broken-reference/)     |   |
| [`DataFrame.shape`](dataframe.shape.md)   |   |

### Conversion

| [`DataFrame.asType`](dataframe.astype.md)   | Cast a pandas object to a specified dtype `dtype`. |
| ------------------------------------------- | -------------------------------------------------- |
| [`DataFrame.copy`](danfo.dataframe.copy.md) | Make a copy of this object’s indices and data.     |

### Indexing, iteration

| [`DataFrame.head`](danfo.dataframe.head.md)   | Return the first n rows                                            |
| --------------------------------------------- | ------------------------------------------------------------------ |
| [`DataFrame.loc`](danfo.dataframe.loc.md)     | Access a group of rows and columns by label(s) or a boolean array. |
| [`DataFrame.iloc`](danfo.dataframe.iloc.md)   | Purely integer-location based indexing for selection by position.  |
| [`DataFrame.tail`](danfo.dataframe.tail.md)   | Return the last n rows.                                            |
| [`DataFrame.query`](danfo.dataframe.query.md) | Query the columns of a DataFrame with a boolean expression.        |

### Binary operator functions

| [`DataFrame.add`](danfo.dataframe.add.md) | Get Addition of dataframe and other, element-wise (binary operator add).                |
| ----------------------------------------- | --------------------------------------------------------------------------------------- |
| [`DataFrame.sub`](danfo.dataframe.sub.md) | Get Subtraction of dataframe and other, element-wise (binary operator sub).             |
| [`DataFrame.mul`](danfo.dataframe.mul.md) | Get Multiplication of dataframe and other, element-wise (binary operator mul).          |
| [`DataFrame.div`](danfo.dataframe.div.md) | Get Floating division of dataframe and other, element-wise (binary operator truediv).   |
| [`DataFrame.mod`](danfo.dataframe.mod.md) | Get Modulo of dataframe and other, element-wise (binary operator mod).                  |
| [`DataFrame.pow`](danfo.dataframe.pow.md) | Get Exponential power of dataframe and other, element-wise (binary operator pow).       |
| [`DataFrame.lt`](broken-reference/)       | Get Less than of dataframe and other, element-wise (binary operator lt).                |
| [`DataFrame.gt`](danfo.dataframe.gt.md)   | Get Greater than of dataframe and other, element-wise (binary operator gt).             |
| [`DataFrame.le`](danfo.dataframe.le.md)   | Get Less than or equal to of dataframe and other, element-wise (binary operator le).    |
| [`DataFrame.ge`](broken-reference/)       | Get Greater than or equal to of dataframe and other, element-wise (binary operator ge). |
| [`DataFrame.ne`](danfo.dataframe.ne.md)   | Get Not equal to of dataframe and other, element-wise (binary operator ne).             |
| [`DataFrame.eq`](danfo.dataframe.eq.md)   | Get Equal to of dataframe and other, element-wise (binary operator eq).                 |

### Function application & GroupBy

| [`DataFrame.apply`](danfo.dataframe.apply.md) | Apply a function along an axis of the DataFrame.          |
| --------------------------------------------- | --------------------------------------------------------- |
| [`DataFrame.groupby`](../groupby/)            | Group DataFrame using a mapper or by a Series of columns. |
| [`DataFrame.map`](../series/series.map.md)    | Map a function on Object along an axis to DataFrame       |

### Computations / descriptive stats

| [`DataFrame.abs`](danfo.dataframe.abs.md)           | Return a Series/DataFrame with absolute numeric value of each element. |
| --------------------------------------------------- | ---------------------------------------------------------------------- |
| [`DataFrame.corr`](broken-reference/)               | Compute pairwise correlation of columns, excluding NA/null values.     |
| [`DataFrame.count`](danfo.dataframe.count.md)       | Count non-NAN cells for each column or row.                            |
| [`DataFrame.cumMax`](danfo.dataframe.cummax.md)     | Return cumulative maximum over a DataFrame or Series axis.             |
| [`DataFrame.cumMin`](danfo.dataframe.cummin.md)     | Return cumulative minimum over a DataFrame or Series axis.             |
| [`DataFrame.cumProd`](danfo.dataframe.cumprod.md)   | Return cumulative product over a DataFrame or Series axis.             |
| [`DataFrame.cumSum`](danfo.dataframe.cumsum.md)     | Return cumulative sum over a DataFrame or Series axis.                 |
| [`DataFrame.describe`](danfo.dataframe.describe.md) | Generate descriptive statistics.                                       |
| [`DataFrame.max`](danfo.dataframe.max.md)           | Return the maximum of the values for the requested axis.               |
| [`DataFrame.mean`](danfo.dataframe.mean.md)         | Return the mean of the values for the requested axis.                  |
| [`DataFrame.median`](danfo.dataframe.median.md)     | Return the median of the values for the requested axis.                |
| [`DataFrame.min`](danfo.dataframe.min.md)           | Return the minimum of the values for the requested axis.               |
| [`DataFrame.mode`](../series/series.mode.md)        | Get the mode(s) of each element along the selected axis.               |
| [`DataFrame.round`](danfo.dataframe.round.md)       | Round a DataFrame to a variable number of decimal places.              |
| [`DataFrame.sum`](danfo.dataframe.sum.md)           | Return the sum of the values for the requested axis.                   |
| [`DataFrame.std`](danfo.dataframe.std.md)           | Return sample standard deviation over requested axis.                  |
| [`DataFrame.var`](danfo.dataframe.var.md)           | Return unbiased variance over requested axis.                          |
| [`DataFrame.nUnique`](broken-reference/)            | Count distinct observations over requested axis.                       |

### Reindexing / selection / label manipulation

|                                                     |                                                         |
| --------------------------------------------------- | ------------------------------------------------------- |
| [`DataFrame.drop`](dataframe.drop.md)               | Drop specified labels from rows or columns.             |
| [`DataFrame.head`](danfo.dataframe.head.md)         | Return the first n rows.                                |
| [`DataFrame.rename`](dataframe.rename.md)           | Alter axes labels.                                      |
| [`DataFrame.resetIndex`](dataframe.reset\_index.md) | Reset the index of a DataFrame                          |
| [`DataFrame.sample`](danfo.dataframe.sample.md)     | Return a random sample of items from an axis of object. |
| [`DataFrame.setIndex`](dataframe.set\_index.md)     | Set the DataFrame index using existing columns.         |
| [`DataFrame.tail`](danfo.dataframe.tail.md)         | Return the last n rows.                                 |

### Missing data handling

|                                                   |                                             |
| ------------------------------------------------- | ------------------------------------------- |
| [`DataFrame.dropNa`](danfo.dataframe.dropna.md)   | Remove missing values.                      |
| [`DataFrame.fillNa`](danfo.dataframe.fillna.md)   | Fill NaN values with specified values       |
| [`DataFrame.isNa`](danfo.dataframe.isna.md)       | Detect missing values.                      |
| [`DataFrame.replace`](danfo.dataframe.replace.md) | Replace values given in replace with value. |

### Sorting & transposing

|                                                                                                                        |                                       |
| ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------- |
| [`DataFrame.sortVlues`](dataframe.sort\_values.md)                                                                     | Sort by the values along either axis. |
| [`DataFrame.T`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.T.html#pandas.DataFrame.T) | Return transpose of DataFrame         |

### Combining / comparing / joining / merging

|                                                            |                                                                     |
| ---------------------------------------------------------- | ------------------------------------------------------------------- |
| [`DataFrame.addColumn`](danfo.dataframe.addcolumn.md)      | Add new columns to a DataFrame.                                     |
| [`DataFrame.concat`](../general-functions/danfo.concat.md) | Concatenate DataFrames together.                                    |
| [`DataFrame.merge`](../general-functions/danfo.merge.md)   | Merge DataFrame or named Series objects with a database-style join. |

### Plotting

`Series.plot` is both a callable method and a namespace attribute for specific plotting methods of the form `Series.plot.<kind>`.

|                                                          |                                                               |
| -------------------------------------------------------- | ------------------------------------------------------------- |
| [DataFrame.plot.bar](../plotting/bar-charts.md)          | Vertical bar plot.                                            |
| [`DataFrame.plot.box`](../plotting/box-plots.md)         | Make a box plot of the DataFrame columns.                     |
| [`DataFrame.plot.violin`](../plotting/box-plots.md)      | Make a violin plot of the DataFrame columns.                  |
| [`DataFrame.plot.hist`](../plotting/histograms.md)       | Draw one histogram of the DataFrame’s columns.                |
| [`DataFrame.plot.scatter`](../plotting/scatter-plots.md) | Generate Kernel Density Estimate plot using Gaussian kernels. |
| [`DataFrame.plot.line`](../plotting/line-charts.md)      | Plot Series or DataFrame as lines.                            |
| [`DataFrame.plot.pie`](../plotting/pie-charts.md)        | Generate a pie plot.                                          |
| [`Timeseries Plots`](../plotting/timeseries-plots.md)    | Time series plots                                             |
| [`Table`](../plotting/tables.md)                         | Display Series as Interactive table in Div                    |

### Serialization / IO / conversion

|                                                               |                                  |
| ------------------------------------------------------------- | -------------------------------- |
| [`DataFrame.toCSV`](dataframe.to\_csv.md)                     | Convert DataFrame to a CSV file. |
| [`DataFrame.toJSON`](dataframe.to\_json.md)                   | Convert the object to a JSON.    |
| ``[`DataFrame.toExcel`](../input-output/danfo.to\_excel.md)`` | Convert DataFrame to Excel file  |
