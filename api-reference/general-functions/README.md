---
description: Top level functions that can be called from the Danfo namespace
---

# General Functions

### Data manipulations

|  |  |
| :--- | :--- |
| [`merge`](danfo.merge.md) | Merge DataFrame or named Series objects with a database-style join. |
| [`concat`](danfo.concat.md) | Concatenate danfo objects along a particular axis with optional set logic along the other axes. |
| [`get_dummies`](danfo.get_dummies.md) | Convert categorical variable into dummy/indicator variables. Similar to OneHotEncoding |

### Data Processing/Normalization

| [LabelEncoder](danfo.labelencoder.md) | Encode target labels with value between 0 and n\_classes-1. |
| :--- | :--- |
| [OneHotEncoder](danfo.onehotencoder.md) | Encode categorical features as a one-hot numeric array. |
| [StandardScaler](danfo.standardscaler.md) | Standardize features by removing the mean and scaling to unit variance |
| [`MinMaxScaler`](danfo.minmaxscaler.md) | Transform features by scaling each feature to a given range |

### Top-level dealing with datetime

| [`to_datetime`](danfo.to_datetime.md) | Convert argument to datetime. |
| :--- | :--- |
| [`date_range`](danfo.date_range.md) | Return a fixed frequency DatetimeIndex. |

