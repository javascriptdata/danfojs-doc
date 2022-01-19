---
description: >-
  Plot Series or DataFrame as lines. This function is useful to plot lines using
  DataFrame’s values as coordinates.
---

# Line Charts

## Examples

### Basic Line plot on Series

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.jsdelivr.net/npm/danfojs@1.0.2/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

        const s = new dfd.Series([1, 3, 2, 6, 10, 34, 40, 51, 90, 75])
        s.plot("plot_div").line()

    </script>
</body>

</html>
```

![](<../../.gitbook/assets/newplot (4).png>)

### Line plots on DataFrame

The example below shows the plot of column values against a common x-axis (index)

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <script src="https://cdn.jsdelivr.net/npm/danfojs@1.0.2/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

        const df = new dfd.DataFrame({'pig': [20, 18, 489, 675, 1776],
                               'horse': [4, 25, 281, 600, 1900]}, {index: [1990, 1997, 2003, 2009, 2014]})
        df.plot("plot_div").line()

    </script>
</body>

</html>
```

![](<../../.gitbook/assets/newplot (2).png>)

The example below shows how to plot two columns in a DataFrame against each other.

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <script src="https://cdn.plot.ly/plotly-1.2.0.min.js"></script> 
     <script src="https://cdn.jsdelivr.net/npm/danfojs@1.0.2/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>
    
      const df = new dfd.DataFrame({
        'pig': [20, 18, 489, 675, 1776],
        'horse': [4, 25, 281, 600, 1900]
      }, { index: [1990, 1997, 2003, 2009, 2014] })
  
      df.plot("plot_div").line({
        config: {
          x: 'pig', y: 'horse'
        }
      })

    </script>
</body>

</html>
```

![](<../../.gitbook/assets/newplot (3).png>)

{% hint style="info" %}
To customize your plots, see the [Customize your plot page](configuring-your-plots.md)
{% endhint %}
