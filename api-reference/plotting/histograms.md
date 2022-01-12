---
description: Draw one histogram of the DataFrame’s columns, or single histogram for Series
---

# Histograms

A histogram is a representation of the distribution of data. This function groups the values of all given Series in the DataFrame into bins

## Examples

### Histogram of a Column in a DataFrame

In the example below, we make an histogram from the `Age` column in the titanic dataset.

{% tabs %}
{% tab title="React" %}
```tsx
import { useEffect } from 'react';
import './App.css';
import { readCSV } from "danfojs-nightly";

function App() {

  useEffect(() => {
    readCSV("https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/titanic.csv")
      .then(df => {

        df['Age'].plot("plot_div").hist()

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
    dfd.readCSV("https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/titanic.csv")
      .then(df => {

        df['Age'].plot("plot_div").hist()

      }).catch(err => {
        console.log(err);
      })
  </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

![](<../../.gitbook/assets/newplot (10).png>)

### Customized Histogram plots on DataFrame

{% tabs %}
{% tab title="React" %}
```tsx
import { useEffect } from 'react';
import './App.css';
import { readCSV } from "danfojs-nightly";

function App() {

  useEffect(() => {
    readCSV("https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/titanic.csv")
      .then(df => {

        const layout = {
          bargap: 0,
          bargroupgap: 0.1,
          title: "Histogram of two columns stacked",
          xaxis: { title: "Value" },
          yaxis: { title: "Count" }
        }

        const sub_df = df.loc({ columns: ["Fare", "Age"] })
        sub_df.plot("plot_div").hist({ layout })

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
a
```
{% endtab %}

{% tab title="Browser" %}
```tsx
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <script src="https://cdn.jsdelivr.net/npm/danfojs@0.3.3/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>
      dfd.readCSV("https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/titanic.csv")
        .then(df => {
  
          const layout = {
            bargap: 0,
            bargroupgap: 0.1,
            title: "Histogram of two columns stacked",
            xaxis: { title: "Value" },
            yaxis: { title: "Count" }
          }
  
          const sub_df = df.loc({ columns: ["Fare", "Age"] })
          sub_df.plot("plot_div").hist({ layout })
  
        }).catch(err => {
          console.log(err);
        })

    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

![](<../../.gitbook/assets/newplot (20).png>)

{% hint style="info" %}
For more configuration options for Histograms, see the [Plotly](https://plotly.com/javascript/histograms/) doc.
{% endhint %}
