---
description: 'Two-dimensional, size-mutable, potentially heterogeneous tabular data.'
---

# Dataframe

> [`DataFrame`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html#pandas.DataFrame)\(data, {**columns:** \[ Array \], **dtypes:** \[ Array \], **index:** \[Array\]}\) \[[source](https://github.com/opensource9ja/danfojs/blob/3398c2f540c16ac95599a05b6f2db4eff8a258c9/danfojs/src/core/frame.js#L20)\]

### Attributes and underlying data

| [`DataFrame.index`](dataframe.index.md) | The index \(row labels\) of the DataFrame. |
| :--- | :--- |
| [`DataFrame.columns`](danfo.dataframe.column.md) | The column labels of the DataFrame. |

| [`DataFrame.dtypes`](dataframe.dtypes.md) | Return the dtypes in the DataFrame. |
| :--- | :--- |
| [`DataFrame.select_dtypes`](dataframe.select_dtypes.md) | Return a subset of the DataFrame’s columns based on the column dtypes. |
| [`DataFrame.values`](dataframe.values.md) | Return a Numpy representation of the DataFrame. |
| [`DataFrame.axes`](dataframe.axes.md) | Return a Object representing the axes of the DataFrame. |
| [`DataFrame.ndim`](dataframe.ndim.md) | Return an int representing the number of axes / array dimensions. |
| [`DataFrame.size`](dataframe.size.md) | Return an int representing the number of elements in this object. |
| [`DataFrame.shape`](dataframe.shape.md) | Return a tuple representing the dimensionality of the DataFrame. |

### Conversion

| [`DataFrame.astype`](dataframe.astype.md) | Cast a pandas object to a specified dtype `dtype`. |
| :--- | :--- |
| [`DataFrame.copy`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.copy.html#pandas.DataFrame.copy) | Make a copy of this object’s indices and data. |

### Indexing, iteration

| [`DataFrame.head`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.head.html#pandas.DataFrame.head) | Return the first n rows |
| :--- | :--- |
| [`DataFrame.loc`](danfo.dataframe.loc.md) | Access a group of rows and columns by label\(s\) or a boolean array. |
| [`DataFrame.iloc`](danfo.dataframe.iloc.md) | Purely integer-location based indexing for selection by position. |
| [`DataFrame.tail`](danfo.dataframe.tail.md) | Return the last n rows. |
| [`DataFrame.query`](danfo.dataframe.query.md) | Query the columns of a DataFrame with a boolean expression. |

### Binary operator functions

| [`DataFrame.add`](danfo.dataframe.add.md) | Get Addition of dataframe and other, element-wise \(binary operator add\). |
| :--- | :--- |
| [`DataFrame.sub`](danfo.dataframe.sub.md) | Get Subtraction of dataframe and other, element-wise \(binary operator sub\). |
| [`DataFrame.mul`](danfo.dataframe.mul.md) | Get Multiplication of dataframe and other, element-wise \(binary operator mul\). |
| [`DataFrame.div`](danfo.dataframe.div.md) | Get Floating division of dataframe and other, element-wise \(binary operator truediv\). |
| [`DataFrame.mod`](danfo.dataframe.mod.md) | Get Modulo of dataframe and other, element-wise \(binary operator mod\). |
| [`DataFrame.pow`](danfo.dataframe.pow.md) | Get Exponential power of dataframe and other, element-wise \(binary operator pow\). |
| [`DataFrame.lt`](dataframe.lt.md) | Get Less than of dataframe and other, element-wise \(binary operator lt\). |
| [`DataFrame.gt`](danfo.dataframe.gt.md) | Get Greater than of dataframe and other, element-wise \(binary operator gt\). |
| [`DataFrame.le`](danfo.dataframe.le.md) | Get Less than or equal to of dataframe and other, element-wise \(binary operator le\). |
| [`DataFrame.ge`]() | Get Greater than or equal to of dataframe and other, element-wise \(binary operator ge\). |
| [`DataFrame.ne`](danfo.dataframe.ne.md) | Get Not equal to of dataframe and other, element-wise \(binary operator ne\). |
| [`DataFrame.eq`](danfo.dataframe.eq.md) | Get Equal to of dataframe and other, element-wise \(binary operator eq\). |

### Function application & GroupBy

| [`DataFrame.apply`](danfo.dataframe.apply.md) | Apply a function along an axis of the DataFrame. |
| :--- | :--- |
| [`DataFrame.groupby`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.groupby.html#pandas.DataFrame.groupby) | Group DataFrame using a mapper or by a Series of columns. |
| [`DataFrame.map`](../series/danfo.series.map.md) | Map a function on Object along an axis to DataFrame |

### Computations / descriptive stats

| [`DataFrame.abs`](danfo.dataframe.abs.md) | Return a Series/DataFrame with absolute numeric value of each element. |
| :--- | :--- |
| [`DataFrame.corr`](dataframe.corr.md) | Compute pairwise correlation of columns, excluding NA/null values. |
| [`DataFrame.count`](danfo.dataframe.count.md) | Count non-NAN cells for each column or row. |
| [`DataFrame.cummax`](danfo.dataframe.cummax.md) | Return cumulative maximum over a DataFrame or Series axis. |
| [`DataFrame.cummin`](danfo.dataframe.cummin.md) | Return cumulative minimum over a DataFrame or Series axis. |
| [`DataFrame.cumprod`](danfo.dataframe.cumprod.md) | Return cumulative product over a DataFrame or Series axis. |
| [`DataFrame.cumsum`](danfo.dataframe.cumsum.md) | Return cumulative sum over a DataFrame or Series axis. |
| [`DataFrame.describe`](danfo.dataframe.describe.md) | Generate descriptive statistics. |
| [`DataFrame.max`](danfo.dataframe.max.md) | Return the maximum of the values for the requested axis. |
| [`DataFrame.mean`](danfo.dataframe.mean.md) | Return the mean of the values for the requested axis. |
| [`DataFrame.median`](danfo.dataframe.median.md) | Return the median of the values for the requested axis. |
| [`DataFrame.min`](danfo.dataframe.min.md) | Return the minimum of the values for the requested axis. |
| [`DataFrame.mode`](../series/danfo.series.mode.md) | Get the mode\(s\) of each element along the selected axis. |
| [`DataFrame.round`](danfo.dataframe.round.md) | Round a DataFrame to a variable number of decimal places. |
| [`DataFrame.sum`](danfo.dataframe.sum.md) | Return the sum of the values for the requested axis. |
| [`DataFrame.std`](danfo.dataframe.std.md) | Return sample standard deviation over requested axis. |
| [`DataFrame.var`](danfo.dataframe.var.md) | Return unbiased variance over requested axis. |
| [`DataFrame.nunique`](dataframe.nunique.md) | Count distinct observations over requested axis. |

### Reindexing / selection / label manipulation

|  |  |
| :--- | :--- |
| [`DataFrame.drop`](dataframe.drop.md) | Drop specified labels from rows or columns. |
| [`DataFrame.head`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.head.html#pandas.DataFrame.head) | Return the first n rows. |
| [`DataFrame.rename`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.rename.html#pandas.DataFrame.rename) | Alter axes labels. |
| [`DataFrame.reset_index`](dataframe.reset_index.md) | Reset the index of a DataFrame |
| [`DataFrame.sample`](danfo.dataframe.sample.md) | Return a random sample of items from an axis of object. |
| [`DataFrame.set_index`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.set_index.html#pandas.DataFrame.set_index) | Set the DataFrame index using existing columns. |
| [`DataFrame.tail`](danfo.dataframe.tail.md) | Return the last n rows. |

### Missing data handling

|  |  |
| :--- | :--- |
| [`DataFrame.dropna`](danfo.dataframe.dropna.md) | Remove missing values. |
| [`DataFrame.fillna`](danfo.dataframe.fillna.md) | Fill NaN values with specified values |
| [`DataFrame.isna`](danfo.dataframe.isna.md) | Detect missing values. |
| [`DataFrame.replace`](danfo.dataframe.replace.md) | Replace values given in replace with value. |

### Sorting & transposing

|  |  |
| :--- | :--- |
| [`DataFrame.sort_values`](dataframe.sort_values.md) | Sort by the values along either axis. |
| [`DataFrame.T`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.T.html#pandas.DataFrame.T) | Return transpose of DataFrame |
| [`DataFrame.transpose`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.transpose.html#pandas.DataFrame.transpose) | Transpose index and columns. |

### Combining / comparing / joining / merging

|  |  |
| :--- | :--- |
| [`DataFrame.addColumn`](danfo.dataframe.addcolumn.md) | Add new columns to a DataFrame. |
| [`DataFrame.concat`](danfo.dataframe.concat.md) | Concatenate DataFrames together. |
| [`DataFrame.merge`](danfo.dataframe.merge.md) | Merge DataFrame or named Series objects with a database-style join. |



### Plotting

`DataFrame.plot` exposes different plot methods that work in the browser. All plots are compatible with Plotly API. 

| [`DataFrame.plot`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.plot.html#pandas.DataFrame.plot) | DataFrame plotting accessor and method |
| :--- | :--- |


|  |  |
| :--- | :--- |
| [`DataFrame.plot.bar`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.plot.bar.html#pandas.DataFrame.plot.bar) | Vertical bar plot. |
| [`DataFrame.plot.box`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.plot.box.html#pandas.DataFrame.plot.box) | Make a box plot of the DataFrame columns. |
| [`DataFrame.plot.density`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.plot.density.html#pandas.DataFrame.plot.density) | Generate Kernel Density Estimate plot using Gaussian kernels. |
| [`DataFrame.plot.hist`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.plot.hist.html#pandas.DataFrame.plot.hist) | Draw one histogram of the DataFrame’s columns. |
| [`DataFrame.plot.kde`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.plot.kde.html#pandas.DataFrame.plot.kde) | Generate Kernel Density Estimate plot using Gaussian kernels. |
| [`DataFrame.plot.line`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.plot.line.html#pandas.DataFrame.plot.line) | Plot Series or DataFrame as lines. |
| [`DataFrame.plot.pie`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.plot.pie.html#pandas.DataFrame.plot.pie) | Generate a pie plot. |
| [`DataFrame.plot.scatter`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.plot.scatter.html#pandas.DataFrame.plot.scatter) | Create a scatter plot with varying marker point size and color. |

### Serialization / IO / conversion

|  |  |
| :--- | :--- |
| [`DataFrame.to_csv`](dataframe.to_csv.md) | Write object to a comma-separated values \(csv\) file. |
| [`DataFrame.to_json`](dataframe.to_json.md) | Convert the object to a JSON string. |
| [`DataFrame.to_table`](dataframe.to_table.md) | Render a DataFrame as an HTML table. |
| [`DataFrame.toString`](../series/danfo.series.tostring.md) | Render a DataFrame to a console-friendly tabular output. |
| [`DataFrame.print`](dataframe.print.md) | Display a DataFrame to a console friendly output. |

