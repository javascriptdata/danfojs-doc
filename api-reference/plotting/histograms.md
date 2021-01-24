---
description: 'Draw one histogram of the DataFrame’s columns, or single histogram for Series'
---

# Histograms

A histogram is a representation of the distribution of data. This function groups the values of all given Series in the DataFrame into bins

## Examples

### Histogram of a Column in a DataFrame

In the example below, we use the titanic dataset, to show a close to a real-world use case of danfo.js

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <!--danfojs CDN -->
    <script src="https://cdn.jsdelivr.net/gh/opensource9ja/danfojs@latest/lib/bundle.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

         dfd.read_csv("https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/titanic.csv")
            .then(df => {

                df['Age'].plot("plot_div").hist()

            }).catch(err => {
                console.log(err);
            })

    </script>
</body>

</html>

```

![](../../.gitbook/assets/newplot-10-.png)

### Customized Histogram plots on DataFrame

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <!--danfojs CDN -->
    <script src="https://cdn.jsdelivr.net/gh/opensource9ja/danfojs@latest/lib/bundle.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

        dfd.read_csv("https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/titanic.csv")
            .then(df => {

                var layout = {
                    bargap: 0,
                    bargroupgap: 0.1,
                    barmode: "stack",
                    title: "Histogram of two columns stacked",
                    xaxis: { title: "Value" },
                    yaxis: { title: "Count" }
                }

                sub_df = df.loc({ columns: ["Fare", "Age"] })
                sub_df.plot("plot_div").hist({layout: layout })

            }).catch(err => {
                console.log(err);
            })

    </script>
</body>

</html>

```

![](../../.gitbook/assets/newplot-20-.png)

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

df.plot("div_tag").histogram({layout: layout})
```

{% hint style="info" %}
For more configuration options for Histograms, see the [Plotly](https://plotly.com/javascript/histograms/) style doc.
{% endhint %}

