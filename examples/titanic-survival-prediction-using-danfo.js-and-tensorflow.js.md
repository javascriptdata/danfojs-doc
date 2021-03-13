---
description: >-
  The titanic survival prediction is a classic problem in the data science
  space. In this tutorial, you are going to create a regression model to predict
  who will survive the disaster.
---

# Titanic Survival Prediction using Danfo.js and Tensorflow.js

> The RMS Titanic was a British passenger liner that sank in the North Atlantic Ocean in the early morning hours of 15 April 1912, after it collided with an iceberg during its maiden voyage from Southampton to New York City. There were an estimated 2,224 passengers and crew aboard the ship, and more than 1,500 died, making it one of the deadliest commercial peacetime maritime disasters in modern history. The RMS Titanic was the largest ship afloat at the time it entered service and was the second of three Olympic-class ocean liners operated by the White Star Line. The Titanic was built by the Harland and Wolff shipyard in Belfast. Thomas Andrews, her architect, died in the disaster. \([Wikipedia](https://en.wikipedia.org/wiki/Titanic)\)



In this tutorial, I will show you how to load and process the famous Titanic dataset with danfo.js, and also how to create a deep learning model with Tensorflow.js to predict survival. This is a classic problem used to introduce new concepts in the field of Machine Learning. 

The main objective of this tutorial is to show you how to use danfo.js to load and process data easily in JavaScript, so we won't be doing anything too advanced. Also, I assumed that you're familiar with basic deep learning with Tensorflow.js and Pandas as well. If you do not have any background in ML, these are good resources to get started:

* [Introduction to Machine Learning](https://developers.google.com/machine-learning/crash-course/ml-intro) 
* [Deep Learning and Neural Networks](https://www.tensorflow.org/resources/learn-ml/basics-of-machine-learning)
* [A Gentle Introduction to TensorFlow.js](https://blog.tensorflow.org/2018/04/a-gentle-introduction-to-tensorflowjs.html)

### Setting up your environment

Danfo.js comes in two builds. There's the browser-based build, optimized for browser environments, and there is the node.js version optimized for Node.js environment. 

In this tutorial, you're going to use the Node.js build. If you do not have Node.js installed, following the guide [here](https://nodejs.org/en/). When you're done, create a new project by running the command below in a terminal opened in your preferred terminal.

```javascript
npm init
```

Fill in the necessary details to create your app. Next, in your terminal, install danfo.js:

**Update \(14th Feb 2021\):** 

Danfo now ships with an exported version of tensorflow \(v2.8.5\). This is exported under the namespace `tf`. This fixes the **double registration of runtime** issue many users have faced in the past. 

```javascript
npm install danfojs-node
```

When you're done, create a file called app.js and import the packages:

```javascript
const dfd = require("danfojs-node")
const tf = dfd.tf //Reference to the exported tensorflowjs library
```

### Loading and processing your data

To load a CSV dataset, you can use the [read\_csv](../api-reference/input-output/danfo.read_csv.md) function. This can load a file from both a local path, as well as over the internet. In this tutorial, you'll load the titanic dataset from the internet.

Below your import add the following lines of code:

```javascript
async function load_process_data() {
    
    let df = await dfd.read_csv("https://web.stanford.edu/class/archive/cs/cs109/cs109.1166/stuff/titanic.csv")
    df.head().print()
    
    
}
```

```text
 Shape: (5,8) 

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Survived          │ Pclass            │ Name              │ Sex               │ ...               │ Age               │ Siblings/Spou...  │ Parents/Child...  │ Fare              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 0                 │ 3                 │ Mr. Owen Harr...  │ male              │ ...               │ 22                │ 1                 │ 0                 │ 7.25              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 1                 │ Mrs. John Bra...  │ female            │ ...               │ 38                │ 1                 │ 0                 │ 71.2833           ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 1                 │ 3                 │ Miss. Laina H...  │ female            │ ...               │ 26                │ 0                 │ 0                 │ 7.925             ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 1                 │ 1                 │ Mrs. Jacques ...  │ female            │ ...               │ 35                │ 1                 │ 0                 │ 53.1              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ 0                 │ 3                 │ Mr. William H...  │ male              │ ...               │ 35                │ 0                 │ 0                 │ 8.05              ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

You wrote an async function because loading dataset over the internet takes a few seconds depending on your network. Inside the async function, you pass in the url of the titanic dataset to the read\_csv function. 

Next you'll perform some basic data preprocessing. The [ctypes](../api-reference/dataframe/dataframe.dtypes.md) attribute returns the column data types:

```javascript
df.ctypes.print()
```

```javascript
╔═════════════════════════╤══════════════════════╗
║                         │ 0                    ║
╟─────────────────────────┼──────────────────────╢
║ Survived                │ int32                ║
╟─────────────────────────┼──────────────────────╢
║ Pclass                  │ int32                ║
╟─────────────────────────┼──────────────────────╢
║ Name                    │ string               ║
╟─────────────────────────┼──────────────────────╢
║ Sex                     │ string               ║
╟─────────────────────────┼──────────────────────╢
║ Age                     │ int32                ║
╟─────────────────────────┼──────────────────────╢
║ Siblings/Spouses Aboard │ int32                ║
╟─────────────────────────┼──────────────────────╢
║ Parents/Children Aboard │ int32                ║
╟─────────────────────────┼──────────────────────╢
║ Fare                    │ float32              ║
╚═════════════════════════╧══════════════════════╝
```

From the data types table above, you'll notice that there are two strong columns. The first is the Name column which contains Names of each passenger. From the head of the dataset you printed above, you'll confirm that each name has a title. So you can extract these titles from the names and this can serve as a new feature. 

```javascript
//A feature engineering: Extract all titles from names columns
let title = df['Name'].apply((x) => { return x.split(".")[0] }).values

//replace in df
df.addColumn({ column: "Name", value: title })
```

In the code above, you are calling the [apply](../api-reference/series/series.apply.md) function on the _**Name**_ column. The parameter to the [apply](../api-reference/series/series.apply.md) function is a function that gets called on each element of the column. This function can be any JavaScript function. 

So what exactly is the function doing? Well, it is basically slicing each name and extracting the title. And finally, you are using the result to replace the original name column. When you're done, your output becomes:

```text
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Survived          │ Pclass            │ Name              │ Sex               │ ...               │ Age               │ Siblings/Spou...  │ Parents/Child...  │ Fare              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 0                 │ 3                 │ Mr                │ male              │ ...               │ 22                │ 1                 │ 0                 │ 7.25              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 1                 │ Mrs               │ female            │ ...               │ 38                │ 1                 │ 0                 │ 71.2833           ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 1                 │ 3                 │ Miss              │ female            │ ...               │ 26                │ 0                 │ 0                 │ 7.925             ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 1                 │ 1                 │ Mrs               │ female            │ ...               │ 35                │ 1                 │ 0                 │ 53.1              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ 0                 │ 3                 │ Mr                │ male              │ ...               │ 35                │ 0                 │ 0                 │ 8.05              ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

```

You notice we now have titles inplace of names. You can easily one hot encode this feature. You will do that below:

```javascript
//label Encode Name feature
let encoder = new dfd.LabelEncoder()
let cols = ["Sex", "Name"]
cols.forEach(col => {
  encoder.fit(df[col])
  let enc_val = encoder.transform(df[col])
  df.addColumn({ column: col, value: enc_val })
})

df.head().print()
```

In code cell above, you're[ label encoding](../api-reference/general-functions/danfo.labelencoder.md) the Sex and Name column. You loop over each column name, fit the encoder to the column, transform it and finally reassign it to the DataFrame. The output is shown below:

```text

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Survived          │ Pclass            │ Name              │ Sex               │ ...               │ Age               │ Siblings/Spou...  │ Parents/Child...  │ Fare              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 0                 │ 3                 │ 0                 │ 0                 │ ...               │ 22                │ 1                 │ 0                 │ 7.25              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 1                 │ 1                 │ 1                 │ 1                 │ ...               │ 38                │ 1                 │ 0                 │ 71.2833           ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 1                 │ 3                 │ 2                 │ 1                 │ ...               │ 26                │ 0                 │ 0                 │ 7.925             ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 1                 │ 1                 │ 1                 │ 1                 │ ...               │ 35                │ 1                 │ 0                 │ 53.1              ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ 0                 │ 3                 │ 0                 │ 0                 │ ...               │ 35                │ 0                 │ 0                 │ 8.05              ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

Next, you'll split data. You'll separate the features from the labels. In this task, you're trying to predict Survival of a passenger. Survival column is the first in the DataFramw, so you'll use [iloc](../api-reference/dataframe/danfo.dataframe.iloc.md) to subset the DataFrame:

```javascript
let Xtrain,ytrain;
Xtrain = df.iloc({ columns: [`1:`] })
ytrain = df['Survived']
```

Next, you'll scale the data using [MinMaxScaler](../api-reference/general-functions/danfo.minmaxscaler.md). It is important to scale your data before model training, as this will affect training. 

```javascript
// Standardize the data with MinMaxScaler
let scaler = new dfd.MinMaxScaler()
scaler.fit(Xtrain)
Xtrain = scaler.transform(Xtrain)
return [Xtrain.tensor, ytrain.tensor]
```

In the code cell above, first, you create an instance from the MinMaxScaler class. Next, you fit the train data and finally, you transform. The output from the scaler is a DataFrame of same size with the values scaled. 

```text
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ 0                 │ 1                 │ 2                 │ 3                 │ 4                 │ 5                 │ 6                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ 1                 │ 0                 │ 0                 │ 0.27117365598...  │ 0.125             │ 0                 │ 0.01415105722...  ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 0                 │ 0.0625            │ 1                 │ 0.47222921252...  │ 0.125             │ 0                 │ 0.13913573324...  ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 1                 │ 0.125             │ 1                 │ 0.32143753767...  │ 0                 │ 0                 │ 0.01546856947...  ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ 0                 │ 0.0625            │ 1                 │ 0.43453130125...  │ 0.125             │ 0                 │ 0.10364428907...  ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 4 │ 1                 │ 0                 │ 0                 │ 0.43453130125...  │ 0                 │ 0                 │ 0.01571255363...  ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

The full code for the load\_process\_data function becomes:

```javascript
const dfd = require("danfojs-node")
const tf = require("@tensorflow/tfjs-node")

async function load_process_data() {
    let df = await dfd.read_csv("https://web.stanford.edu/class/archive/cs/cs109/cs109.1166/stuff/titanic.csv")

    //A feature engineering: Extract all titles from names columns
    let title = df['Name'].apply((x) => { return x.split(".")[0] }).values
    //replace in df
    df.addColumn({ column: "Name", value: title })

    //label Encode Name feature
    let encoder = new dfd.LabelEncoder()
    let cols = ["Sex", "Name"]
    cols.forEach(col => {
        encoder.fit(df[col])
        let enc_val = encoder.transform(df[col])
        df.addColumn({ column: col, value: enc_val })
    })


    let Xtrain,ytrain;
    Xtrain = df.iloc({ columns: [`1:`] })
    ytrain = df['Survived']

    // Standardize the data with MinMaxScaler
    let scaler = new dfd.MinMaxScaler()
    scaler.fit(Xtrain)
    Xtrain = scaler.transform(Xtrain)

    return [Xtrain.tensor, ytrain.tensor] //return the data as tensors
}

load_process_data()
```

### Model Building With Tensorflow.js

In this section, you'll build a simple classification model using tensorflow.js. If you're not familiar with Tensorflow.js, you can start [here](https://blog.tensorflow.org/2018/04/a-gentle-introduction-to-tensorflowjs.html). 

Create a simple function called get\_model. This will construct and return a model when called. 

```javascript
function get_model() {
    const model = tf.sequential();
    model.add(tf.layers.dense({ inputShape: [7], units: 124, activation: 'relu', kernelInitializer: 'leCunNormal' }));
    model.add(tf.layers.dense({ units: 64, activation: 'relu' }));
    model.add(tf.layers.dense({ units: 32, activation: 'relu' }));
    model.add(tf.layers.dense({ units: 1, activation: "sigmoid" }))
    model.summary();
    return model
}
```

In the code cell above, you created a neural network with 4 layers. Note the input shape, this should be the same as your column numbers. Also, note that you used a sigmoid in the output layer. This is because you're working on a binary classification problem. 

Next, you will create a function called _**train:**_

```javascript

async function train() {
    const model = get_model()
    const data = await load_process_data()
    const Xtrain = data[0]
    const ytrain = data[1]

    model.compile({
        optimizer: "rmsprop",
        loss: 'binaryCrossentropy',
        metrics: ['accuracy'],
    });
    
    console.log("Training started....")
    await model.fit(Xtrain, ytrain,{
        batchSize: 32,
        epochs: 15,
        validationSplit: 0.2,
        callbacks:{
            onEpochEnd: async(epoch, logs)=>{
                console.log(`EPOCH (${epoch + 1}): Train Accuracy: ${(logs.acc * 100).toFixed(2)},
                                                     Val Accuracy:  ${(logs.val_acc * 100).toFixed(2)}\n`);
            }
        }
    });
    
}
```

This function calls the _**load\_process\_data**_ function to retrieve training data as tensors and also calls the _**get\_model**_ to retrieve the model. Next, you compile the model by specifying an optimizer, a loss function and a metric to report.

Next, you call the **fit** function on the model, by passing the training data and labels \(tensors\), specify batch size, epoch size, validation split size, and also a callback function to track training progress. 

The training progress is printed to the console at the end of each Epoch.  Below is the full code from loading data to training your model:

```javascript
const dfd = require("danfojs-node")
const tf = require("@tensorflow/tfjs-node")

async function load_process_data() {
    let df = await dfd.read_csv("https://web.stanford.edu/class/archive/cs/cs109/cs109.1166/stuff/titanic.csv")

    //A feature engineering: Extract all titles from names columns
    let title = df['Name'].apply((x) => { return x.split(".")[0] }).values
    //replace in df
    df.addColumn({ column: "Name", value: title })

    //label Encode Name feature
    let encoder = new dfd.LabelEncoder()
    let cols = ["Sex", "Name"]
    cols.forEach(col => {
        encoder.fit(df[col])
        let enc_val = encoder.transform(df[col])
        df.addColumn({ column: col, value: enc_val })
    })


    let Xtrain,ytrain;
    Xtrain = df.iloc({ columns: [`1:`] })
    ytrain = df['Survived']

    // Standardize the data with MinMaxScaler
    let scaler = new dfd.MinMaxScaler()
    scaler.fit(Xtrain)
    Xtrain = scaler.transform(Xtrain)

    return [Xtrain.tensor, ytrain.tensor] //return the data as tensors
}

load_process_data()


function get_model() {
    const model = tf.sequential();
    model.add(tf.layers.dense({ inputShape: [7], units: 124, activation: 'relu', kernelInitializer: 'leCunNormal' }));
    model.add(tf.layers.dense({ units: 64, activation: 'relu' }));
    model.add(tf.layers.dense({ units: 32, activation: 'relu' }));
    model.add(tf.layers.dense({ units: 1, activation: "sigmoid" }))
    model.summary();
    return model
}

async function train() {
    const model = await get_model()
    const data = await load_process_data()
    const Xtrain = data[0]
    const ytrain = data[1]

    model.compile({
        optimizer: "rmsprop",
        loss: 'binaryCrossentropy',
        metrics: ['accuracy'],
    });

    console.log("Training started....")
    await model.fit(Xtrain, ytrain,{
        batchSize: 32,
        epochs: 15,
        validationSplit: 0.2,
        callbacks:{
            onEpochEnd: async(epoch, logs)=>{
                console.log(`EPOCH (${epoch + 1}): Train Accuracy: ${(logs.acc * 100).toFixed(2)},
                                                     Val Accuracy:  ${(logs.val_acc * 100).toFixed(2)}\n`);
            }
        }
    });
};

train()
```

In your terminal, run the script with node:

```javascript
node app.js
```

This runs the script, and displays training progress after each Epoch as shown below:

```text

Epoch 12 / 15
eta=0.0 ===============================================================================================> 
322ms 455us/step - acc=0.812 loss=0.433 val_acc=0.826 val_loss=0.371 
EPOCH (12): Train Accuracy: 81.24,
                                                     Val Accuracy:  82.58

Epoch 13 / 15
eta=0.0 ===============================================================================================> 
320ms 451us/step - acc=0.808 loss=0.433 val_acc=0.843 val_loss=0.375 
EPOCH (13): Train Accuracy: 80.82,
                                                     Val Accuracy:  84.27

Epoch 14 / 15
eta=0.0 ===============================================================================================> 
329ms 463us/step - acc=0.811 loss=0.434 val_acc=0.843 val_loss=0.370 
EPOCH (14): Train Accuracy: 81.10,
                                                     Val Accuracy:  84.27

Epoch 15 / 15
eta=0.0 ===============================================================================================> 
324ms 457us/step - acc=0.804 loss=0.433 val_acc=0.831 val_loss=0.388 
EPOCH (15): Train Accuracy: 80.39,
                                                     Val Accuracy:  83.15
```

After 15 epochs, you reach an accuracy of about 83%. This can definitely be improved, but for the sake of simplicity, we'll stop here. 

In this tutorial, you have seen how to use danfo.js with tensorflow.js to load and process data, as well as train a neural network. This is similar to the Pandas-Tensorflow packages in Python. 

You also notice that danfo.js provides similar API as Pandas and can easily be picked up by Python developers. 

As an extra task, you can try to do more feature engineering using danfo.js and try to improve the accuracy of your model. 

Go danfo! 😎

