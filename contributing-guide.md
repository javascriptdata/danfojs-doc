---
description: >-
  Contributing guide to danfo.js including set up guide, and a brief intro to
  danfo internals.
---

# Contributing Guide

### Contributing to danfojs

**Table of contents:**

* **TL:DR**
* Where to start?
* Working with the code
  * Version control, Git, and GitHub
  * Getting started with Git
  * Forking
  * Creating a development environment
* Documentation Guidelines
* Writing tests
  * Using mocha
  * Running the test suite
* Contributing your changes to danfojs
  * Committing your code
  * Pushing your changes
  * Review your code and finally, make the pull request
* Danfojs internal (Brief)

## TL:DR

All contributions, bug reports, bug fixes, documentation improvements, enhancements, and ideas are welcome. 

For contributors familiar with open-source,  below is a quick guide to setting up danfojs locally.  

```
git clone https://github.com/opensource9ja/danfojs.git
cd danfojs
git checkout -b <your-branch-name>
```

There are two folders, **danfojs-browser** and **danfojs-node**. If you are contributing a new feature, then you should include it in both versions. If you are doing a bug fix for a single version, then open that folder and install packages. 

For instance, if I want to do some bug fixes in danfojs-node. I can do the following:

```
cd danfojs-node 
yarn ##install all packages 
```

Add my bug fixes and ensure test passes:

```
yarn test ## run test 
```

## Where to start?

For first time contributors, you can find pending issues on the GitHub “issues” page. There are a number of issues listed and "good first issue" where you could start out. Once you’ve found an interesting issue, and have an improvement in mind, next thing is to set up your development environment.

## Working with the code

Now that you have an issue you want to fix, an enhancement to add, or documentation to improve, you need to learn how to work with GitHub and the danfojs code base.

### **Version control, Git, and GitHub**

The danfojs code is hosted on GitHub. To contribute you will need to sign up for a free GitHub account. We use Git for version control to allow many people to work together on this project.

Some great resources for learning Git:

* Official [GitHub pages](http://help.github.com).

### **Getting started with Git¶**

Find [Instructions](http://help.github.com/set-up-git-redirect) for installing git, setting up your SSH key, and configuring git. These steps need to be completed before you can work seamlessly between your local repository and GitHub.

## **Forking the danfojs repo**

You will need your own fork to work on the code. Go to the danfojs [project page](https://github.com/opensource9ja/danfojs) and hit the Fork button.

Next, you will clone your fork to your local machine:

```
git clone https://github.com/opensource9ja/danfojs.git
cd danfojs
```

This creates the directory danfojs and connects your repository to the upstream (main project) repository.

> **All development are done in two folders--**[**danfojs-browser**](https://github.com/opensource9ja/danfojs/tree/master/danfojs-browser)** and **[**danfojs-node**](https://github.com/opensource9ja/danfojs/tree/master/danfojs-node)** folders. The two folders are similar and it is always recommended to pull latest changes from master before development in any of the folder. **

Some Javascript features are supported both in the browser and node environment, and it is recommended to add these to both versions. 

For features that work only in NodeJs environment, especially file related issues, these should be developed and tested in the danfojs-node folder, and the corresponding tests are written there.   

## **Creating a development environment**

To test out code changes, you’ll need to build danfojs, which requires a Nodejs environment.

```python
git clone https://github.com/opensource9ja/danfojs.git
cd danfojs
cd danfojs-browser && yarn ## installs required packages in browser version
cd .. && cd danfojs-node && yarn ## installs required packages in node version
cd .. ## Go back to root folder
yarn test ##Runs test in both node and browser folder
```

> Now you can start adding features or fixing bugs!

## Documentation Guidelines

Documentation helps clarify what a function or a method is doing. It also gives insight to users of the function or methods on what parameters to pass in and know what the function will return.

Sample documentation:

```javascript
 /**
 * Add two series of the same length
 * @param {series1} series1 [Series]
 * @param {series2} series2 [Series]
 * @returns Series
 */
function add_series(series1, series2){

        ...................

        return new Series()
}

```

And for functions that contain more than two argument, keyword argument should be used. Parsing of keyword argument is also applicable to most of the methods in a class

```javascript
/**
 * Join two or more dataframe together along an axis
 * @param {kwargs} kwargs --> {
 *                      df_list: [Array of DataFrame],
 *                      axis : int {0 or 1},
 *                      by_column : String {name of a column},
 *                    }
 * @returns DataFrame 
 */
function join_df(kwargs){
        ........

        return DataFrame
}
```

## **Writing tests**

We strongly encourage contributors to write tests for their code. Like many packages, danfojs uses mocha

All tests should go into the tests subdirectory and place in the corresponding module. The tests folder contains some current examples of tests, and we suggest looking to these for inspiration.

Below is the general Framework to write a test for each module.

{% tabs %}
{% tab title="JavaScript" %}
```javascript
import { assert } from "chai"
import { DataFrame } from '../../src/core/frame'

describe("Name of the class|module", function(){
 
  it("name of the methods| expected result",function(){
    
       //write your test code here
       //use assert.{proprty} to test your code
   })

});
```
{% endtab %}
{% endtabs %}

For a class with lots of methods.

```python
import { assert } from "chai"
import { DataFrame } from '../../src/core/frame'

describe("Name of the class|module", function(){
 
 describe("method name 1", function(){
 
   it("expected result",function(){
     
        //write your test code here
        //use assert.{proprty} to test your code
    })
  })
  
  describe("method name 2", function(){
 
   it("expected result",function(){
     
        //write your test code here
        //use assert.{proprty} to test your code
    })
  })
  .......
});
```

**Example**: Let write a test, to test if the values in a dataframe are off a certain length. Assuming the method to obtain length is values_len()

```javascript
import { assert } from "chai"
import { DataFrame } from '../../src/core/frame'

describe("DataFrame", function(){
    
  describe("value_len", function(){
 
   it("check dataframe length",function(){
     
       let data = [[1,2],[4,5]]
       let columns = ["A","B"]
       let df = new DataFrame(data,{columns: columns})
       
       let expected_result = 2
       
       assert.deepEqual(sf.value_len(), expected_result))
       
       
    })
  })

});
```

### **Running the test case**

To run the test for the module you created,

**1)** Open the package.json 

**2)** change the name of the test file to the file name you want. and don't forget the file is in the test folder

```python
"scripts": {
    "test": "....... danfojs/tests/sub_directory_name/filename",
```

**3)  **run the test, in the danfojs directory terminal

```python
yarn test
```

Learn more about mocha [here](https://mochajs.org)

## Contributing your changes to danfojs

### **Committing your code**

Once you’ve made changes, you can see them by typing:

```
git status
```

Next, you can track your changes using

```
git add .
```

Next, you commit changes using:

```
git commit -m "Enter any commit message here"
```

### **Pushing your changes**

When you want your changes to appear publicly on your GitHub page, you can push to your forked repo with:

```
git push
```

### Review your code and finally, make a pull request

If everything looks good, you are ready to make a pull request. A pull request is how code from a local repository becomes available to the GitHub community and can be reviewed and eventually merged into the master version. To submit a pull request:

1. Navigate to your repository on GitHub
2. Click on the Pull Request button
3. Write a description of your changes in the Preview Discussion tab
4. Click Send Pull Request.

This request then goes to the repository maintainers, and they will review the code and everything looks good, merge it with the master.

**Hooray! You're now a contributor to danfojs. Now go bask in the euphoria!**

## **Danfojs Internals**

In other to contribute to the code base of danfojs, there are some functions and properties provided to make implementation easy.

The main exposed modules are the **Frame** and **Series** module. This module inherits from the **Generic **module.

The **Generic** module consists of the following methods and properties

* `.dtypes`    \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/generic.js#L213)] is used to obtain the dtype for each column
* `.index` \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/generic.js#L250)] to obtain the index for Dataframe or Series
* `.__set_index(label) `  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/generic.js#L257)] to set the index value
* `.__reset_index()`  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/generic.js#L271)] to reset the index in DataFrame and Series
* `.values `   Obtain the values in  DataFrame and Series per rows
* `.col_data` Obtain the values in DataFrame and Series per columns
* `.column_names`  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/generic.js#L305)] Obtain the list of column names
* `.__set_col_types` \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/generic.js#L165)] set the dtype for a column or infer the dtype from it
* `.columns` to  access the column names directly
* `row_data_tensor`  store the tensor representation of the data in DataFrame and Series

The **Frame **module consists of the following methods and properties to aid implementation.

* `__frame_is_compactible_for_operation`  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/frame.js#L1754)]:  check if all the values in a DataFrame are numerical. This helps to check if the numerical operation can be done using the dataframe.
* `.__get_ops_tensors(tensors, axis)`   \[[source\]](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/frame.js#L1767) : obtain tensors from dataframes along axis 0 or 1.
* `.__get_df_from_tensor(val, col_names) `  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/frame.js#L1741)]:  Obtain dataframe from tensor.
* `.__get_tensor_and_idx(df, axis)`  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/frame.js#L928)]:  Obtain tensors, their index value and their axis from dataframe.

The **Series **module contains mostly Generic properties and less special internal properties.

* `__check_series_op_compactibility(other)`  \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L666)]  check if two series are compatible for numerical operation

Lastly, the **Utils** module contains important utility functions.
