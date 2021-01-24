---
description: Create a scatter plot of columns in a DataFrame
---

# Scatter Plots

The coordinates of each point are defined by two DataFrame columns and filled circles are used to represent each point. Scatter plot is useful for visualizing complex correlations between two variables. 

## Examples

### Scatter Plots on Columns in a DataFrame

In the example below, we use the titanic dataset, to show a close to real-world use case of danfo.js

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <!--danfojs CDN -->
    <script src="https://cdn.jsdelivr.net/npm/danfojs@0.1.2/dist/index.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

         dfd.read_csv("https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/titanic.csv")
            .then(df => {
            
                df.plot("plot_div").scatter({ x: "Age", y: "Fare" })

            }).catch(err => {
                console.log(err);
            })

    </script>
</body>

</html>

```

![](../../.gitbook/assets/newplot-8-.png)

### More Examples

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <!--danfojs CDN -->
    <script src="https://cdn.jsdelivr.net/npm/danfojs@0.1.2/dist/index.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

       dfd.read_csv("https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/titanic.csv")
            .then(df => {
            
                sub_df = df.loc({columns: ["Age", "Fare", "Parch", "SibSp"]})
                sub_df.plot("plot_div").scatter()

            }).catch(err => {
                console.log(err);
            })

    </script>
</body>

</html>

```

![](../../.gitbook/assets/newplot-19-.png)

### Configuring your plots

danfo.js plotting uses [Plotly.js](https://plotly.com/javascript) as its backend for plotting. This means you have all the configuration, flexibility and interactiveness of Plotly. 

All [customization](https://plotly.com/javascript/line-charts/) on the plot can be passed as an object of key-value pairs to the config parameter. For example:

```javascript
var layout = {
    title: 'A sample plot',
    xaxis: {
        title: 'X',
    },
    yaxis: {
        title: 'Y',
    }
}

df.plot("div_tag").scatter({x= "col1", y: "col2", layout: layout})
```

{% hint style="info" %}
For more configuration options for Scatter plots, see the [Plotly](https://plotly.com/javascript/line-and-scatter/) style doc.
{% endhint %}

