---
description: Timeseries plot are based on date index
---

# Timeseries Plots

## Examples

In the example below, we plot the yearly trend of a financial dataset. First, we reset the index to the Date column.

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

         dfd.read_csv("https://raw.githubusercontent.com/plotly/datasets/master/finance-charts-apple.csv")
            .then(df => {

                var layout = {
                    title: 'A financial charts',
                    xaxis: {
                        title: 'Date',
                    },
                    yaxis: {
                        title: 'Count',
                    }
                }

                new_df = df.set_index({ key: "Date" })
                new_df.plot("plot_div").line({ columns: ["AAPL.Open", "AAPL.High"], layout: layout })

            }).catch(err => {
                console.log(err);
            })

    </script>
</body>

</html>

```

![](../../.gitbook/assets/newplot-29-.png)
