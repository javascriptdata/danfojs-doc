---
description: Timeseries plot are based on date index
---

# Timeseries Plots

## Examples

In the example below, we plot the yearly trend of a financial dataset. First, we reset the index to the Date column.

{% tabs %}
{% tab title="React" %}
{% code title="App.jsx" %}
```tsx
import { useEffect } from 'react';
import './App.css';
import { readCSV } from "danfojs-nightly";

function App() {

  useEffect(() => {
    readCSV(
      "https://raw.githubusercontent.com/plotly/datasets/master/finance-charts-apple.csv"
    )
      .then((df) => {

        const layout = {
          title: "A financial charts",
          xaxis: {
            title: "Date",
          },
          yaxis: {
            title: "Count",
          },
        };

        const config = {
          columns: ["AAPL.Open", "AAPL.High"],
        };

        const new_df = df.setIndex({ column: "Date" });
        new_df.plot("plot_div").line({ config, layout });
      })
      .catch((err) => {
        console.log(err);
      });

  }, [])

  return (
    <div className="App">
      <header className="App-header">
        <div id="plot_div"></div>
      </header>
    </div>
  );
}

export default App;
```
{% endcode %}
{% endtab %}

{% tab title="Browser" %}
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <script src="https://cdn.jsdelivr.net/npm/danfojs-nightly@1.0.2/lib/bundle.js"></script>
    <title>Document</title>
  </head>

  <body>
    <div id="plot_div"></div>

    <script>
      dfd
        .readCSV(
          "https://raw.githubusercontent.com/plotly/datasets/master/finance-charts-apple.csv"
        )
        .then((df) => {

          const layout = {
            title: "A financial charts",
            xaxis: {
              title: "Date",
            },
            yaxis: {
              title: "Count",
            },
          };

          const config = {
            columns: ["AAPL.Open", "AAPL.High"],
          };

          const new_df = df.setIndex({ column: "Date" });
          new_df.plot("plot_div").line({ config, layout });
        })
        .catch((err) => {
          console.log(err);
        });
    </script>
  </body>
</html>

```
{% endtab %}
{% endtabs %}

![](<../../.gitbook/assets/newplot-29- (2) (1).png>)

{% hint style="info" %}
To set customize your charts, see the [Customizing your plot page](configuring-your-plots.md)
{% endhint %}
