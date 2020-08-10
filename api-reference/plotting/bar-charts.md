---
description: Makes a vertical bar plot.
---

# Bar Charts

A bar plot presents categorical data with rectangular bars with lengths proportional to the values that they represent.

## Examples

### Bar plot on Series

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <!--danfojs CDN -->
    <script src="https://cdn.jsdelivr.net/npm/danfojs@0.0.13/dist/index.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

        s = new dfd.Series([1, 3, 2, 6, 10, 34, 40, 51, 90, 75])
        s.plot("plot_div", {type: "bar"})

    </script>
</body>

</html>

```

![](../../.gitbook/assets/newplot-6-.png)

### Line plot on DataFrame

The example below shows the plot of column values against a common x-axis \(index\)

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <!--danfojs CDN -->
    <script src="https://cdn.jsdelivr.net/npm/danfojs@0.0.13/dist/index.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

        df = new dfd.DataFrame({'pig': [20, 18, 489, 675, 1776],
                               'horse': [4, 25, 281, 600, 1900]}, {index: [1990, 1997, 2003, 2009, 2014]})
        df.plot("plot_div")

    </script>
</body>

</html>

```

![](../../.gitbook/assets/newplot-2-.png)

The example below shows how to plot two columns in a DataFrame against each other.

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <!--danfojs CDN -->
    <script src="https://cdn.jsdelivr.net/npm/danfojs@0.0.13/dist/index.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

        df = new dfd.DataFrame({'pig': [20, 18, 489, 675, 1776],
                               'horse': [4, 25, 281, 600, 1900]}, {index: [1990, 1997, 2003, 2009, 2014]})
        df.plot("plot_div", {x: 'pig', y: 'horse'})

    </script>
</body>

</html>

```

![](../../.gitbook/assets/newplot-3-.png)

### Configuring your plots

danfo.js plotting uses [Plotly.js](https://plotly.com/javascript) as its backend for plotting. This means you have all the configuration, flexibility and interactiveness of Plotly. 

All [customization](https://plotly.com/javascript/line-charts/) on the plot can be passed to the config parameter. For example, in the line plot below, we define a layout for our plot and give it a name. 

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <!--danfojs CDN -->
    <script src="https://cdn.jsdelivr.net/npm/danfojs@0.0.13/dist/index.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

      var layout = {
            title: 'Line and Scatter Plot',
            width: 500,
            height: 600
        }

 
        s = new dfd.Series([1, 3, 2, 6, 10, 34, 40, 51, 90, 75])
        s.plot("plot_div", {layout: layout})
        
    </script>
</body>

</html>

```

![](../../.gitbook/assets/newplot-5-.png)

{% hint style="info" %}
For more configuration options for line plots, see the [Plotly](https://plotly.com/javascript/line-charts/) style doc.
{% endhint %}

{% hint style="info" %}
For more configuration options for line plots, see the [Plotly](https://plotly.com/javascript/line-charts/) style doc.
{% endhint %}

