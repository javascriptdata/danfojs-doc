---
description: Make a box plot from DataFrame columns.
---

# Box Plots

Make a box-and-whisker plot from DataFrame columns, optionally grouped by some other columns. A box plot is a method for graphically depicting groups of numerical data through their quartiles.

## Examples

### Boxplot for a Series Object

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

        s = new dfd.Series([20, 30, 40, 23, 40, 3, 50, 34, 67])
        s.plot("plot_div").box()

    </script>
</body>

</html>

```

![](../../.gitbook/assets/newplot-23-.png)

### Box plots on a DataFrame

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

                sub_df = df.loc({ columns: ["Age", "Fare"] })
                sub_df.plot("plot_div").box()

            }).catch(err => {
                console.log(err);
            })

    </script>
</body>

</html>

```

![](../../.gitbook/assets/screen-shot-2020-08-11-at-1.20.42-am%20%281%29%20%281%29.png)

### Box plot for selected columns in a DataFrame

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

                df.plot("plot_div").box({x: "Survived", y: "Age"})

            }).catch(err => {
                console.log(err);
            })

    </script>
</body>

</html>

```

![](../../.gitbook/assets/newplot-24-.png)



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

df.plot("div_tag").box({layout: layout})
```

{% hint style="info" %}
For more configuration options for Box Plots, see the [Plotly](https://plotly.com/javascript/box-plots/) style doc.
{% endhint %}
