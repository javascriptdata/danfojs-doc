---
description: Generate a pie plot.
---

# Pie Charts

A pie plot is a proportional representation of the numerical data in a column

## Examples

### Pie Chart from Columns in a DataFrame

{% tabs %}
{% tab title="React" %}
```tsx
import { useEffect } from 'react';
import './App.css';
import { DataFrame } from "danfojs-nightly";

function App() {

  useEffect(() => {
    const df = new DataFrame({
      Price: [19, 26, 55],
      Location: ["NG", "GH", "SA"],
      Type: ["Residential", "Non-Residential", "Utility"],
    });

    df.plot("plot_div").pie({ config: { values: "Price", labels: "Type" } });
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
      const df = new dfd.DataFrame({
        Price: [19, 26, 55],
        Location: ["NG", "GH", "SA"],
        Type: ["Residential", "Non-Residential", "Utility"],
      });

      df.plot("plot_div").pie({ config: { values: "Price", labels: "Type" } });
    </script>
  </body>
</html>
e
```
{% endtab %}
{% endtabs %}

![](../../.gitbook/assets/newplot-12-.png)

### Multiple Pie Chart from Columns in a DataFrame

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.plot.ly/plotly-1.2.0.min.js"></script> 
     <script src="https://cdn.jsdelivr.net/npm/danfojs@1.2.0/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

       const df = new dfd.DataFrame({
          Price: [19, 26, 55],
          Volume: [100, 200, 300],
          Location: ["NG", "GH", "SA"],
          Type: ["Residential", "Non-Residential", "Utility"],
        });
    
        df.plot("plot_div").pie({
          config: {
            labels: "Location",
            columns: ["Price", "Volume"],
            columnPositions: [0, 1],
          }
        });

    </script>
</body>

</html>
```

![](../../.gitbook/assets/newplot-21-.png)

### Configure Position of Pie Charts

If you have more than one pie chart to display, you can set the grid parameter, and also the position of each pie.

For example, in the snippet below, we set the `grid` to 2 by 2 and also pass a set of row and column index positions. Each row/column position index corresponds to each pie.

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <script src="https://cdn.jsdelivr.net/npm/danfojs@1.2.0/lib/bundle.min.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

       df = new dfd.DataFrame({
            Price: [19, 26, 55],
            Count: [20, 50, 25],
            Type: ['Residential', 'Non-Residential', 'Utility']
        })

        df.plot("plot_div").pie({
          config: {
            labels: "Location",
            columns: ["Price", "Volume"],
            columnPositions: [0, 1],
            rowPositions: [0, 1],
            grid: { rows: 2, columns: 2 }
          }
        });

    </script>
</body>

</html>
```

![](../../.gitbook/assets/newplot-22-.png)

{% hint style="info" %}
For more configuration options for Pie Charts, see the [Plotly](https://plotly.com/javascript/pie-charts/) style doc.
{% endhint %}
