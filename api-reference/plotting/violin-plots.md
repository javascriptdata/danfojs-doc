# Violin Plots

Make a violin plot from DataFrame columns, optionally grouped by some other columns. A violin plot is a method for graphically depicting groups of numerical data through their quartiles. See also [Box Plot](box-plots.md)

## Examples

### Boxplot for a Series Object

{% tabs %}
{% tab title="React" %}
{% code title="App.jsx" %}
```tsx
import { useEffect } from 'react';
import './App.css';
import { Series } from "danfojs-nightly";

function App() {

  useEffect(() => {
       const s = new Series([20, 30, 40, 23, 40, 3, 50, 34, 67])
      s.plot("plot_div").violin()

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
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <script src="https://cdn.jsdelivr.net/npm/danfojs@1.1.0/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

        s = new dfd.Series([20, 30, 40, 23, 40, 3, 50, 34, 67])
        s.plot("plot_div").violin()
         
    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

![](<../../.gitbook/assets/newplot (25).png>)

### Box plots on a DataFrame

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
      "https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/titanic.csv"
    )
      .then((df) => {
        const sub_df = df.loc({ columns: ["Age", "Fare"] });
        sub_df.plot("plot_div").violin();
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
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <script src="https://cdn.jsdelivr.net/npm/danfojs@1.1.0/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

          dfd.read_csv("https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/titanic.csv")
            .then(df => {

                sub_df = df.loc({ columns: ["Age", "Fare"] })
                sub_df.plot("plot_div").violin()

            }).catch(err => {
                console.log(err);
            })

    </script>
</body>

</html>
```
{% endtab %}
{% endtabs %}

![](<../../.gitbook/assets/newplot (26).png>)

### Box plot for selected columns in a DataFrame

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
      "https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/titanic.csv"
    )
      .then((df) => {
        df.plot("plot_div").violin({ config: { x: "Survived", y: "Age" }, layout: { title: "Violin Plot" } });
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

    <div id="plot_div"></div>
    <script>
      dfd
        .readCSV(
          "https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/titanic.csv"
        )
        .then((df) => {
          df.plot("plot_div").violin({ config: { x: "Survived", y: "Age" } });
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

![](<../../.gitbook/assets/newplot (27).png>)

{% hint style="info" %}
To customize your plots, see the [Configuring your plot page](configuring-your-plots.md)
{% endhint %}
