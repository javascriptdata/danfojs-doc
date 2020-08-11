# Contributing Guide



### Contributing to danfojs

**Table of contents:**

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

#### Where to start?

All contributions, bug reports, bug fixes, documentation improvements, enhancements, and ideas are welcome.

For first time contributors, you can find pending issues on the GitHub “issues” page. There are a number of issues listed and "good first issue" where you could start out. Once you’ve found an interesting issue, and have an improvement in mind, next thing is to set up your development environment.

#### Working with the code

Now that you have an issue you want to fix, enhancement to add, or documentation to improve, you need to learn how to work with GitHub and the danfojs code base.

**Version control, Git, and GitHub**

The danfojs code is hosted on GitHub. To contribute you will need to sign up for a free GitHub account. We use Git for version control to allow many people to work together on this project.

Some great resources for learning Git:

* Official [GitHub pages](http://help.github.com).

**Getting started with Git¶**

Find [Instructions](http://help.github.com/set-up-git-redirect) for installing git, setting up your SSH key, and configuring git. These steps need to be completed before you can work seamlessly between your local repository and GitHub.

**Forking the danfojs repo**

You will need your own fork to work on the code. Go to the danfojs [project page](https://github.com/opensource9ja/danfojs) and hit the Fork button.

Next, you will clone your fork to your local machine:

```text
git clone https://github.com/opensource9ja/danfojs.git
```

This creates the directory danfojs and connects your repository to the upstream \(main project\) repository.

**Creating a development environment**

To test out code changes, you’ll need to build danfojs from source, which requires a Nodejs environment.

**1\) Install Nodejs:**

               ****install Nodejs using [NPM ](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)

**2\)** Open the danfojs  directory you git clone with terminal or vscode

**3\)** If using Vscode, click on Terminal ---&gt; click New Terminal

**4\)** In the terminal type in

```python
npm install
```

#### Documentation Guidelines

Documentation helps clarify what a function or a method is doing. It also gives insight t user of the function or methods on what parameters to pass in and know what the function will return.

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

And for functions that contains more than two argument, keyword argument should be used. Parsing of keyword argument is also applicable to most of the methods in a class

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

**Writing tests**

We strongly encourages contributors to write test for their code. Like many packages, danfojs uses mocha

All tests should go into the tests subdirectory and placed in the corresponding module. The tests folder contains some current examples of tests, and we suggest looking to these for inspiration.

Below is the general Framework to write test for each module.

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

For class with lots of method.

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

**Example**: Let write a test, to test if the values in a dataframe are off a certain length. Assuming the method to obtain length is values\_len\(\)

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

**Running the test case**

To run the test for the module you created,

**1\)** Open the package.json 

**2\)** change the name of the test file to the file name you want. and don't forget the file is in the test folder

```python
"scripts": {
    "test": "....... danfojs/tests/sub_directory_name/filename",
```

For now the test directory is  splitted into  Four sub directory; **config, core,io, preprocessing.**

**3\)**  run the test, in the danfojs directory terminal

```python
npm run test
```

Learn more about mocha [here](https://mochajs.org/)

#### Contributing your changes to danfojs

**Committing your code**

Once you’ve made changes, you can see them by typing:

```text
git status
```

Next, you can track your changes using

```text
git add .
```

Next, you commit changes using:

```text
git commit -m "Enter any commit message here"
```

**Pushing your changes**

When you want your changes to appear publicly on your GitHub page, you can push to your forked repo with:

```text
git push
```

#### Review your code and finally, make the pull request

If everything looks good, you are ready to make a pull request. A pull request is how code from a local repository becomes available to the GitHub community and can be reviewed and eventually merged into the master version. To submit a pull request:

1. Navigate to your repository on GitHub
2. Click on the Pull Request button
3. Write a description of your changes in the Preview Discussion tab
4. Click Send Pull Request.

This request then goes to the repository maintainers, and they will review the code and everything looks good, merge it with the master.

**Hooray! Youre now a contributor to danfojs. Now go bask in the euphoria!**



**Danfojs Internals**

In other to contribute to the code base of danfojs, there are some functions  and properties provided to make implementation easy.

The main exposed modules are the **Frame** and **Series** module. This module inherit from the **Generic** module.

The **Generic** module consist of the following methods and properties

* `.dtypes`  is used to obtain the dtype for each column
* `.index` to obtain the index for Dataframe or Series
* `.__set_index(label)`  to set the index value
* `.__reset_index()`  to reset the index in DataFrame and Series
* `.values`    Obtain the values in  DataFrame and Series per rows
* `.col_data` Obtain the values in DataFrame and Series per columns
* `.column_names` Obtain the list of column names
* `.__set_col_types` set the dtype for a column or infer the dtype from it
* `.columns` to  access the column names directly

The **Frame** module consist of the following methods and properties to aid implementation.

* 
