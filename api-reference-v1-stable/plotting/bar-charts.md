---
description: Makes a vertical bar plot.
---

# Bar Charts

A bar plot presents categorical data with rectangular bars with lengths proportional to the values that they represent.

## Examples

The **bar** plot is exposed by the .**plot()** function called on a Series or DataFrame. The **.plot()** method accepts an HTML Div id where it renders the plot, while configuration options for the bars drawn can be passed through the config parameter.

### Bar plot on Series

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <script src="https://cdn.plot.ly/plotly-1.2.0.min.js"></script> 
     <script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

        s = new dfd.Series([1, 3, 2, 6, 10, 34, 40, 51, 90, 75])
        s.plot("plot_div").bar()

    </script>
</body>

</html>
```

![](<../../.gitbook/assets/newplot (6).png>)

### Bar plot on DataFrame

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <script src="https://cdn.plot.ly/plotly-1.2.0.min.js"></script> 
     <script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>
</head>

<body>

    <div id="plot_div"></div>
    <script>

        df = new dfd.DataFrame({'pig': [20, 18, 489, 675, 1776],
                               'horse': [4, 25, 281, 600, 1900]}, {index: [1990, 1997, 2003, 2009, 2014]})
        df.plot("plot_div").bar()

    </script>
</body>

</html>
```

![](<../../.gitbook/assets/newplot (7).png>)

{% hint style="info" %}
To set configuration for your plots, see the [Configuring your plot page](configuring-your-plots.md)
{% endhint %}
