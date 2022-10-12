---
description: Turn DataFrame/Series in D3.js-based tables
---

# Tables

## Examples

### Create Interactive Tables from DataFrame

{% tabs %}
{% tab title="React" %}
{% code title="App.jsx" %}
```tsx
import { useEffect } from 'react';
import './App.css';
import { Series, readCSV } from "danfojs-nightly";

function App() {

  useEffect(() => {
    readCSV("https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/titanic.csv")
      .then(df => {

        df.plot("plot_div").table()
      }).catch(err => {
        console.log(err);
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

    <div id="plot_div"></div>
    <script>
      dfd
        .readCSV(
          "https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/titanic.csv"
        )
        .then((df) => {
          df.plot("plot_div").table()
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

![](<../../.gitbook/assets/Screen Shot 2020-08-11 at 12.34.08 AM.png>)

### Configure the header and cell of a table

To configure the header and cell of a table, you can pass header/cell styles to the **header\_style** and **cell\_style** parameter. The [Plotly table](https://plotly.com/javascript/table/) doc shows numerous configuration options you can pass.

{% tabs %}
{% tab title="React" %}
{% code title="App.jsx" %}
```tsx
import { useEffect } from 'react';
import './App.css';
import { Series, readCSV } from "danfojs-nightly";

function App() {

  useEffect(() => {
    readCSV("https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/titanic.csv")
      .then(df => {

        const headerStyle = {
          align: "center",
          fill: { color: ['gray'] },
          font: { family: "Arial", size: 15, color: "white" },
          
        }
        const cellStyle = {
          align: ["center"],
          line: { color: "black", width: 10 }
        }

        df.plot("plot_div").table({
          config: {
            tableHeaderStyle: headerStyle,
            tableCellStyle: cellStyle
          },
          layout: {
            title: "Table displaying the Titanic dataset",
          }
        })


      }).catch(err => {
        console.log(err);
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

    <div id="plot_div"></div>
    <script>
      dfd
        .readCSV(
          "https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/titanic.csv"
        )
        .then((df) => {
          const headerStyle = {
            align: "center",
            fill: { color: ["gray"] },
            font: { family: "Arial", size: 15, color: "white" },
            columnwidth: 200,
          };
          const cellStyle = {
            align: ["center"],
            line: { color: "black", width: 10 },
          };

          df.plot("plot_div").table({
            config: {
              tableHeaderStyle: headerStyle,
              tableCellStyle: cellStyle,
            },
            layout: {
              title: "Table displaying the Titanic dataset",
            },
          });

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

![](<../../.gitbook/assets/Screen Shot 2020-08-11 at 12.38.30 AM.png>)
