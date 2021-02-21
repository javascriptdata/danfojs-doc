---
description: >-
  Plot Series or DataFrame as lines. This function is useful to plot lines using
  DataFrame’s values as coordinates.
---

# Line Charts

## Examples

### Basic Line plot on Series

The **line** plot is exposed by the .**plot\(\)** function called on a Series or DataFrame. The **.plot\(\)** method accepts an HTML Div id where it renders the plot, while configuration options for the lines drawn can be passed through the config parameter.

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

        s = new dfd.Series([1, 3, 2, 6, 10, 34, 40, 51, 90, 75])
        s.plot("plot_div").line()

    </script>
</body>

</html>

```

![](../../.gitbook/assets/newplot-4-.png)

### Line plots on DataFrame

The example below shows the plot of column values against a common x-axis \(index\)

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

        df = new dfd.DataFrame({'pig': [20, 18, 489, 675, 1776],
                               'horse': [4, 25, 281, 600, 1900]}, {index: [1990, 1997, 2003, 2009, 2014]})
        df.plot("plot_div").line()

    </script>
</body>

</html>

```

![](../../.gitbook/assets/newplot-2-%20%281%29.png)

The example below shows how to plot two columns in a DataFrame against each other.

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

        df = new dfd.DataFrame({'pig': [20, 18, 489, 675, 1776],
                               'horse': [4, 25, 281, 600, 1900]}, {index: [1990, 1997, 2003, 2009, 2014]})
        df.plot("plot_div").line({x: 'pig', y: 'horse'})

    </script>
</body>

</html>

```

![](../../.gitbook/assets/newplot-3-.png)

### Configuring your plots

danfo.js plotting uses [Plotly.js](https://plotly.com/javascript) as its backend for plotting. This means you have all the configuration, flexibility and interactiveness of Plotly.

All [customization](https://plotly.com/javascript/line-charts/) on the plot can be passed as an object of key-value pairs to the config parameter. For example, in the line plot below, we define a layout for our plot and give it a name.

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

      var layout = {
            title: 'Line and Scatter Plot',
            width: 500,
            height: 600
        }


        s = new dfd.Series([1, 3, 2, 6, 10, 34, 40, 51, 90, 75])
        s.plot("plot_div").line({ layout: layout })

    </script>
</body>

</html>

```

![](../../.gitbook/assets/newplot-5-.png)

{% hint style="info" %}
For more configuration options for line plots, see the [Plotly](https://plotly.com/javascript/line-charts/) style doc.
{% endhint %}
