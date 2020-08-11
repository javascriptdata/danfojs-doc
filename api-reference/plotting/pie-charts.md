---
description: Generate a pie plot.
---

# Pie Charts

A pie plot is a proportional representation of the numerical data in a column

## Examples

### Pie Chart from Columns in a DataFrame

In the example below, we use the titanic dataset, to show a close to real world use case of danfo.js

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

         df = new dfd.DataFrame({
            Price: [19, 26, 55],
            Location: ["NG", "GH", "SA"],
            Type: ['Residential', 'Non-Residential', 'Utility']
        })
        
        df.plot("plot_div", { values: "Price", labels: "Type", type: "pie" })

    </script>
</body>

</html>

```

![](../../.gitbook/assets/newplot-12-.png)

{% hint style="info" %}
For more configuration options for Pie Charts, see the [Plotly](https://plotly.com/javascript/pie-charts/) style doc.
{% endhint %}

