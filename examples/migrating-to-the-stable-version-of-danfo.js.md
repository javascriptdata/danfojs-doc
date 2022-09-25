---
description: >-
  This page contains migration guides and tips for pre-v1 users of Danfo.js who
  want to migrate their projects to the latest stable release of Danfo.js.
---

# Migrating to the stable version of Danfo.js

We recently released the first stable version of Danfo.js. See release note here. This new version improves previous versions, by standardizing the API. As such we now have better naming conventions, class structures, and error messages.

The following list summarizes some of these updates:

* **Typescript support:** This new version has been completely re-written using Typescript. This means we now have well-defined types that increase the developer experience.
* **Standard naming convention:** Functions, methods, classes, and variable names have been standardized to follow JavaScript best practices.
* Standardize function argument: Functions and methods have been updated to accept arguments and parameters intuitively resulting in improved developer experience.
* **New features**: We added a couple of new features which users have been requesting for. For example:
  * Stream and process large CSV data
* General bug fixes and improvements
* Better error messages

## Breaking Updates

There are two major breaking changes in the new stable version.

### Naming convention

Update your function and/or method names to use camelCase instead of snake\_case. For example:

```javascript
read_csv ==> readCSV
to_json ==> toJSON
drop_duplicates ==> dropDuplicates
```

**Note:** that your code editor will generally suggest the new function or method names, so it will be easier to update to the new names. If using Typescript, then it is even easier as the TS compiler will show you warnings.

### Functions and Methods argument structure

Another major breaking change of v1, is that the structure of arguments/parameters in most functions has been updated to be more intuitive.

In general, it is important to understand our thought process behind this, so, here goes:

Assuming we take the method called _**rename**_, which takes the required argument **mapper**, as well as, an optional configuration argument. In pre-v1 version of Danfojs, the function signature is as follows:

```
rename( { mapper, axis, inplace } ) => DataFrame
```

The structure above combines both required and optional arguments as a single object argument, which is less intuitive. A better method signature will/should take into account the required and optional arguments, as well as their position. Hence we need something like:

```
rename(mapper, options: {axis, inplace}) //where mapper is required, and options argument is optional. 
```

Re-designing functions and methods to follow this intuitive format is the bulk of the breaking change in this new version, as such, when migrating, you have to make these updates.

{% hint style="info" %}
If using Typescript, then the TS compiler will help in migration, else, you have to manually identify and update your function/method signature.
{% endhint %}

### Axis Order

In this new version, we have flipped the result of the axis ordering for all operations. This ordering is now consistent with Pandas and Tensorflow.js. That is, the axis row (0), represents the operations carried out horizontally on a DataFrame, and the axis columns (1) represent operations carried out vertically down the DataFrame.

{% hint style="info" %}
In short, when migrating to the new version, you should flip the axis number so as to get the same result. That is, change all `axis: 0` to `axis: 1`, to get the same result.
{% endhint %}

All examples in this doc have been updated to reflect this update.
