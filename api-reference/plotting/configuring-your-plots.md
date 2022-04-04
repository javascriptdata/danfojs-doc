# Customizing your plots

Danfo.js currently supports [Plotly.js](https://plotly.com/javascript) for plotting. This means you have all the configuration, flexibility, and interactiveness of Plotly.

All [customization](https://plotly.com/javascript/line-charts/) on the plot can be passed in the `config` and `layout` parameter.

## Config Parameter

The config parameter extends the [Plotly.js config](https://plotly.com/javascript/configuration-options/) type. That is, all properties available to the Plotly [config](https://plotly.com/javascript/configuration-options/) argument, are available. Alongside those arguments, Danfo.js uses some custom arguments which we list below:

| Argument             | Description                                                                                                                                                                                    | Default value                                |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------- |
| **x**                | Column name to plot on the x-axis.                                                                                                                                                             | DataFrame index if required                  |
| **y**                | Column name to plot on the y-axis.                                                                                                                                                             | DataFrame index if required                  |
| **columns**          | Array of column names to plot.                                                                                                                                                                 | All columns in the DataFrame when applicable |
| **values**           | Used to configure a `pie` chart. A column name containing values for the pie. Maps 1-1 with labels.                                                                                            |                                              |
| **labels**           | Used to configure a `pie` chart. A column name containing labels for the pie. Maps 1-1 with values.                                                                                            |                                              |
| **rowPositions**     | Used to configure a `pie` chart. Pie chart domain row. See [https://plotly.com/javascript/reference/pie/#pie-domain-row](https://plotly.com/javascript/reference/pie/#pie-domain-row)          | Range of `0 - DataFrame column length`       |
| **columnPositions**  | Used to configure a `pie` chart. Pie chart domain column. See [https://plotly.com/javascript/reference/pie/#pie-domain-column](https://plotly.com/javascript/reference/pie/#pie-domain-column) | Range of `0 - DataFrame column length`       |
| **grid**             | <p>Used to configure a <code>pie</code> chart. Accepts the following parameter:<br><br><strong>row</strong>: Integer size<br><strong>column</strong>: Integer size</p>                         |                                              |
| **tableHeaderStyle** | Table properties used for configuring table header. See [full list](https://plotly.com/javascript/reference/table/#table-header) of supported arguments.                                       |                                              |
| **tableCellStyle**   | Table properties used for configuring table cells. See [full list](https://plotly.com/javascript/reference/table/#table-header) of supported arguments                                         |                                              |

## Layout Parameter

The `layout` argument object is used to configure the overall display of a chart. See the full list of supported [arguments](https://plotly.com/javascript/reference/layout/)

In the following example, we show how to set some basic configuration as well as layout for a line plot.

{% tabs %}
{% tab title="React" %}
```tsx
import { useEffect } from 'react';
import './App.css';
import { readCSV } from "danfojs-nightly";

function App() {

  useEffect(() => {

    readCSV("https://raw.githubusercontent.com/plotly/datasets/master/finance-charts-apple.csv")
      .then(df => {

        const layout = {
          title: {
            text: "Time series plot of AAPL open and close points",
            x: 0
          },
          legend: {
            bgcolor: "#fcba03",
            bordercolor: "#444",
            borderwidth: 1,
            font: { family: "Arial", size: 10, color: "#fff" }
          },
          width: 1000,
          yaxis: {
            title: 'AAPL open points',
          },
          xaxis: {
            title: 'Date',
          },
        }

        const config = {
          columns: ["AAPL.Open", "AAPL.Close"], //columns to plot
          displayModeBar: true,
          displaylogo: false,
        }
        df.plot("plot_div").line({ layout, config })
      })
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
            title: {
              text: "Time series plot of AAPL open and close points",
              x: 0,
            },
            legend: {
              bgcolor: "#fcba03",
              bordercolor: "#444",
              borderwidth: 1,
              font: { family: "Arial", size: 10, color: "#fff" },
            },
            width: 1000,
            yaxis: {
              title: "AAPL open points",
            },
            xaxis: {
              title: "Date",
            },
          };

          const config = {
            columns: ["AAPL.Open", "AAPL.Close"], //columns to plot
            displayModeBar: true,
            displaylogo: false,
          };
          df.plot("plot_div").line({ layout, config });
        });
    </script>
  </body>
</html>
```
{% endtab %}
{% endtabs %}

![](<../../.gitbook/assets/newplot (32).png>)

##
