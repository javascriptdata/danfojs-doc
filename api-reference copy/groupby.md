---
description: >-
  GroupBy objects are returned by groupby calls: danfo.DataFrame.groupby(),
  danfo.Series.groupby()
---

# Groupby

### Indexing, iteration

| [`GroupBy.__iter__`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.__iter__.html#pandas.core.groupby.GroupBy.__iter__)\(\) | Groupby iterator. |
| :--- | :--- |
| [`GroupBy.groups`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.groups.html#pandas.core.groupby.GroupBy.groups) | Dict {group name -&gt; group labels}. |
| [`GroupBy.indices`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.indices.html#pandas.core.groupby.GroupBy.indices) | Dict {group name -&gt; group indices}. |
| [`GroupBy.get_group`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.get_group.html#pandas.core.groupby.GroupBy.get_group)\(name\[, obj\]\) | Construct DataFrame from group with provided name. |

| [`Grouper`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Grouper.html#pandas.Grouper)\(\*args, \*\*kwargs\) | A Grouper allows the user to specify a groupby instruction for an object. |
| :--- | :--- |


### Function application

| [`GroupBy.apply`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.apply.html#pandas.core.groupby.GroupBy.apply)\(func, \*args, \*\*kwargs\) | Apply function func group-wise and combine the results together. |
| :--- | :--- |
| [`GroupBy.agg`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.agg.html#pandas.core.groupby.GroupBy.agg)\(func, \*args, \*\*kwargs\) |  |
| [`SeriesGroupBy.aggregate`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.SeriesGroupBy.aggregate.html#pandas.core.groupby.SeriesGroupBy.aggregate)\(\[func, engine, …\]\) | Aggregate using one or more operations over the specified axis. |
| [`DataFrameGroupBy.aggregate`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.aggregate.html#pandas.core.groupby.DataFrameGroupBy.aggregate)\(\[func, engine, …\]\) | Aggregate using one or more operations over the specified axis. |
| [`SeriesGroupBy.transform`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.SeriesGroupBy.transform.html#pandas.core.groupby.SeriesGroupBy.transform)\(func, \*args\[, …\]\) | Call function producing a like-indexed Series on each group and return a Series having the same indexes as the original object filled with the transformed values |
| [`DataFrameGroupBy.transform`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.transform.html#pandas.core.groupby.DataFrameGroupBy.transform)\(func, \*args\[, …\]\) | Call function producing a like-indexed DataFrame on each group and return a DataFrame having the same indexes as the original object filled with the transformed values |
| [`GroupBy.pipe`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.pipe.html#pandas.core.groupby.GroupBy.pipe)\(func, \*args, \*\*kwargs\) | Apply a function func with arguments to this GroupBy object and return the function’s result. |

### Computations / descriptive stats

| [`GroupBy.all`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.all.html#pandas.core.groupby.GroupBy.all)\(\[skipna\]\) | Return True if all values in the group are truthful, else False. |
| :--- | :--- |
| [`GroupBy.any`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.any.html#pandas.core.groupby.GroupBy.any)\(\[skipna\]\) | Return True if any value in the group is truthful, else False. |
| [`GroupBy.bfill`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.bfill.html#pandas.core.groupby.GroupBy.bfill)\(\[limit\]\) | Backward fill the values. |
| [`GroupBy.backfill`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.backfill.html#pandas.core.groupby.GroupBy.backfill)\(\[limit\]\) | Backward fill the values. |
| [`GroupBy.count`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.count.html#pandas.core.groupby.GroupBy.count)\(\) | Compute count of group, excluding missing values. |
| [`GroupBy.cumcount`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.cumcount.html#pandas.core.groupby.GroupBy.cumcount)\(\[ascending\]\) | Number each item in each group from 0 to the length of that group - 1. |
| [`GroupBy.cummax`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.cummax.html#pandas.core.groupby.GroupBy.cummax)\(\[axis\]\) | Cumulative max for each group. |
| [`GroupBy.cummin`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.cummin.html#pandas.core.groupby.GroupBy.cummin)\(\[axis\]\) | Cumulative min for each group. |
| [`GroupBy.cumprod`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.cumprod.html#pandas.core.groupby.GroupBy.cumprod)\(\[axis\]\) | Cumulative product for each group. |
| [`GroupBy.cumsum`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.cumsum.html#pandas.core.groupby.GroupBy.cumsum)\(\[axis\]\) | Cumulative sum for each group. |
| [`GroupBy.ffill`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.ffill.html#pandas.core.groupby.GroupBy.ffill)\(\[limit\]\) | Forward fill the values. |
| [`GroupBy.first`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.first.html#pandas.core.groupby.GroupBy.first)\(\[numeric\_only, min\_count\]\) | Compute first of group values. |
| [`GroupBy.head`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.head.html#pandas.core.groupby.GroupBy.head)\(\[n\]\) | Return first n rows of each group. |
| [`GroupBy.last`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.last.html#pandas.core.groupby.GroupBy.last)\(\[numeric\_only, min\_count\]\) | Compute last of group values. |
| [`GroupBy.max`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.max.html#pandas.core.groupby.GroupBy.max)\(\[numeric\_only, min\_count\]\) | Compute max of group values. |
| [`GroupBy.mean`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.mean.html#pandas.core.groupby.GroupBy.mean)\(\[numeric\_only\]\) | Compute mean of groups, excluding missing values. |
| [`GroupBy.median`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.median.html#pandas.core.groupby.GroupBy.median)\(\[numeric\_only\]\) | Compute median of groups, excluding missing values. |
| [`GroupBy.min`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.min.html#pandas.core.groupby.GroupBy.min)\(\[numeric\_only, min\_count\]\) | Compute min of group values. |
| [`GroupBy.ngroup`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.ngroup.html#pandas.core.groupby.GroupBy.ngroup)\(\[ascending\]\) | Number each group from 0 to the number of groups - 1. |
| [`GroupBy.nth`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.nth.html#pandas.core.groupby.GroupBy.nth)\(n\[, dropna\]\) | Take the nth row from each group if n is an int, or a subset of rows if n is a list of ints. |
| [`GroupBy.ohlc`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.ohlc.html#pandas.core.groupby.GroupBy.ohlc)\(\) | Compute open, high, low and close values of a group, excluding missing values. |
| [`GroupBy.pad`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.pad.html#pandas.core.groupby.GroupBy.pad)\(\[limit\]\) | Forward fill the values. |
| [`GroupBy.prod`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.prod.html#pandas.core.groupby.GroupBy.prod)\(\[numeric\_only, min\_count\]\) | Compute prod of group values. |
| [`GroupBy.rank`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.rank.html#pandas.core.groupby.GroupBy.rank)\(\[method, ascending, na\_option, …\]\) | Provide the rank of values within each group. |
| [`GroupBy.pct_change`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.pct_change.html#pandas.core.groupby.GroupBy.pct_change)\(\[periods, fill\_method, …\]\) | Calculate pct\_change of each value to previous entry in group. |
| [`GroupBy.size`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.size.html#pandas.core.groupby.GroupBy.size)\(\) | Compute group sizes. |
| [`GroupBy.sem`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.sem.html#pandas.core.groupby.GroupBy.sem)\(\[ddof\]\) | Compute standard error of the mean of groups, excluding missing values. |
| [`GroupBy.std`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.std.html#pandas.core.groupby.GroupBy.std)\(\[ddof\]\) | Compute standard deviation of groups, excluding missing values. |
| [`GroupBy.sum`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.sum.html#pandas.core.groupby.GroupBy.sum)\(\[numeric\_only, min\_count\]\) | Compute sum of group values. |
| [`GroupBy.var`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.var.html#pandas.core.groupby.GroupBy.var)\(\[ddof\]\) | Compute variance of groups, excluding missing values. |
| [`GroupBy.tail`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.tail.html#pandas.core.groupby.GroupBy.tail)\(\[n\]\) | Return last n rows of each group. |

The following methods are available in both `SeriesGroupBy` and `DataFrameGroupBy` objects, but may differ slightly, usually in that the `DataFrameGroupBy` version usually permits the specification of an axis argument, and often an argument indicating whether to restrict application to columns of a specific data type.

| [`DataFrameGroupBy.all`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.all.html#pandas.core.groupby.DataFrameGroupBy.all)\(\[skipna\]\) | Return True if all values in the group are truthful, else False. |
| :--- | :--- |
| [`DataFrameGroupBy.any`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.any.html#pandas.core.groupby.DataFrameGroupBy.any)\(\[skipna\]\) | Return True if any value in the group is truthful, else False. |
| [`DataFrameGroupBy.backfill`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.backfill.html#pandas.core.groupby.DataFrameGroupBy.backfill)\(\[limit\]\) | Backward fill the values. |
| [`DataFrameGroupBy.bfill`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.bfill.html#pandas.core.groupby.DataFrameGroupBy.bfill)\(\[limit\]\) | Backward fill the values. |
| [`DataFrameGroupBy.corr`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.corr.html#pandas.core.groupby.DataFrameGroupBy.corr) | Compute pairwise correlation of columns, excluding NA/null values. |
| [`DataFrameGroupBy.count`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.count.html#pandas.core.groupby.DataFrameGroupBy.count)\(\) | Compute count of group, excluding missing values. |
| [`DataFrameGroupBy.cov`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.cov.html#pandas.core.groupby.DataFrameGroupBy.cov) | Compute pairwise covariance of columns, excluding NA/null values. |
| [`DataFrameGroupBy.cumcount`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.cumcount.html#pandas.core.groupby.DataFrameGroupBy.cumcount)\(\[ascending\]\) | Number each item in each group from 0 to the length of that group - 1. |
| [`DataFrameGroupBy.cummax`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.cummax.html#pandas.core.groupby.DataFrameGroupBy.cummax)\(\[axis\]\) | Cumulative max for each group. |
| [`DataFrameGroupBy.cummin`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.cummin.html#pandas.core.groupby.DataFrameGroupBy.cummin)\(\[axis\]\) | Cumulative min for each group. |
| [`DataFrameGroupBy.cumprod`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.cumprod.html#pandas.core.groupby.DataFrameGroupBy.cumprod)\(\[axis\]\) | Cumulative product for each group. |
| [`DataFrameGroupBy.cumsum`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.cumsum.html#pandas.core.groupby.DataFrameGroupBy.cumsum)\(\[axis\]\) | Cumulative sum for each group. |
| [`DataFrameGroupBy.describe`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.describe.html#pandas.core.groupby.DataFrameGroupBy.describe)\(\*\*kwargs\) | Generate descriptive statistics. |
| [`DataFrameGroupBy.diff`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.diff.html#pandas.core.groupby.DataFrameGroupBy.diff) | First discrete difference of element. |
| [`DataFrameGroupBy.ffill`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.ffill.html#pandas.core.groupby.DataFrameGroupBy.ffill)\(\[limit\]\) | Forward fill the values. |
| [`DataFrameGroupBy.fillna`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.fillna.html#pandas.core.groupby.DataFrameGroupBy.fillna) | Fill NA/NaN values using the specified method. |
| [`DataFrameGroupBy.filter`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.filter.html#pandas.core.groupby.DataFrameGroupBy.filter)\(func\[, dropna\]\) | Return a copy of a DataFrame excluding filtered elements. |
| [`DataFrameGroupBy.hist`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.hist.html#pandas.core.groupby.DataFrameGroupBy.hist) | Make a histogram of the DataFrame’s. |
| [`DataFrameGroupBy.idxmax`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.idxmax.html#pandas.core.groupby.DataFrameGroupBy.idxmax) | Return index of first occurrence of maximum over requested axis. |
| [`DataFrameGroupBy.idxmin`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.idxmin.html#pandas.core.groupby.DataFrameGroupBy.idxmin) | Return index of first occurrence of minimum over requested axis. |
| [`DataFrameGroupBy.mad`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.mad.html#pandas.core.groupby.DataFrameGroupBy.mad) | Return the mean absolute deviation of the values for the requested axis. |
| [`DataFrameGroupBy.nunique`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.nunique.html#pandas.core.groupby.DataFrameGroupBy.nunique)\(\[dropna\]\) | Return DataFrame with counts of unique elements in each position. |
| [`DataFrameGroupBy.pad`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.pad.html#pandas.core.groupby.DataFrameGroupBy.pad)\(\[limit\]\) | Forward fill the values. |
| [`DataFrameGroupBy.pct_change`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.pct_change.html#pandas.core.groupby.DataFrameGroupBy.pct_change)\(\[periods, …\]\) | Calculate pct\_change of each value to previous entry in group. |
| [`DataFrameGroupBy.plot`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.plot.html#pandas.core.groupby.DataFrameGroupBy.plot) | Class implementing the .plot attribute for groupby objects. |
| [`DataFrameGroupBy.quantile`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.quantile.html#pandas.core.groupby.DataFrameGroupBy.quantile)\(\[q, interpolation\]\) | Return group values at the given quantile, a la numpy.percentile. |
| [`DataFrameGroupBy.rank`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.rank.html#pandas.core.groupby.DataFrameGroupBy.rank)\(\[method, ascending, …\]\) | Provide the rank of values within each group. |
| [`DataFrameGroupBy.resample`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.resample.html#pandas.core.groupby.DataFrameGroupBy.resample)\(rule, \*args, \*\*kwargs\) | Provide resampling when using a TimeGrouper. |
| [`DataFrameGroupBy.sample`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.sample.html#pandas.core.groupby.DataFrameGroupBy.sample)\(\[n, frac, replace, …\]\) | Return a random sample of items from each group. |
| [`DataFrameGroupBy.shift`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.shift.html#pandas.core.groupby.DataFrameGroupBy.shift)\(\[periods, freq, …\]\) | Shift each group by periods observations. |
| [`DataFrameGroupBy.size`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.size.html#pandas.core.groupby.DataFrameGroupBy.size)\(\) | Compute group sizes. |
| [`DataFrameGroupBy.skew`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.skew.html#pandas.core.groupby.DataFrameGroupBy.skew) | Return unbiased skew over requested axis. |
| [`DataFrameGroupBy.take`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.take.html#pandas.core.groupby.DataFrameGroupBy.take) | Return the elements in the given _positional_ indices along an axis. |
| [`DataFrameGroupBy.tshift`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.tshift.html#pandas.core.groupby.DataFrameGroupBy.tshift) | \(DEPRECATED\) Shift the time index, using the index’s frequency if available. |

The following methods are available only for `SeriesGroupBy` objects.

| [`SeriesGroupBy.hist`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.SeriesGroupBy.hist.html#pandas.core.groupby.SeriesGroupBy.hist) | Draw histogram of the input series using matplotlib. |
| :--- | :--- |
| [`SeriesGroupBy.nlargest`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.SeriesGroupBy.nlargest.html#pandas.core.groupby.SeriesGroupBy.nlargest) | Return the largest n elements. |
| [`SeriesGroupBy.nsmallest`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.SeriesGroupBy.nsmallest.html#pandas.core.groupby.SeriesGroupBy.nsmallest) | Return the smallest n elements. |
| [`SeriesGroupBy.nunique`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.SeriesGroupBy.nunique.html#pandas.core.groupby.SeriesGroupBy.nunique)\(\[dropna\]\) | Return number of unique elements in the group. |
| [`SeriesGroupBy.unique`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.SeriesGroupBy.unique.html#pandas.core.groupby.SeriesGroupBy.unique) | Return unique values of Series object. |
| [`SeriesGroupBy.value_counts`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.SeriesGroupBy.value_counts.html#pandas.core.groupby.SeriesGroupBy.value_counts)\(\[normalize, …\]\) |  |
| [`SeriesGroupBy.is_monotonic_increasing`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.SeriesGroupBy.is_monotonic_increasing.html#pandas.core.groupby.SeriesGroupBy.is_monotonic_increasing) | Alias for is\_monotonic. |
| [`SeriesGroupBy.is_monotonic_decreasing`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.SeriesGroupBy.is_monotonic_decreasing.html#pandas.core.groupby.SeriesGroupBy.is_monotonic_decreasing) | Return boolean if values in the object are monotonic\_decreasing. |

The following methods are available only for `DataFrameGroupBy` objects.

| [`DataFrameGroupBy.corrwith`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.corrwith.html#pandas.core.groupby.DataFrameGroupBy.corrwith) | Compute pairwise correlation. |
| :--- | :--- |
| [`DataFrameGroupBy.boxplot`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.boxplot.html#pandas.core.groupby.DataFrameGroupBy.boxplot)\(\[subplots, column, …\]\) | Make box plots from DataFrameGroupBy data. |

