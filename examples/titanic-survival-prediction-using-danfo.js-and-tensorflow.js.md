---
description: >-
  The titanic survival prediction is a classic problem in the data science
  space. In this tutorial, you are going to create a regression model to predict
  who will survive the disaster.
---

# Titanic Survival Prediction using Danfo.js and Tensorflow.js



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
        enc_val = encoder.transform(df[col])
        df.addColumn({ column: col, value: enc_val })
    })
   
    let Xtrain,ytrain;
    Xtrain = df.iloc({ columns: [`1:`] })
    ytrain = df['Survived']

    // Standardize the data with MinMaxScaler
    let scaler = new dfd.MinMaxScaler()
    scaler.fit(Xtrain)
    Xtrain = scaler.transform(Xtrain)
    return [Xtrain.tensor, ytrain.tensor]


}

async function get_model() {
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

