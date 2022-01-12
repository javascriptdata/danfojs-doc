---
description: Create a scatter plot of columns in a DataFrame
---

# Scatter Plots

The coordinates of each point are defined by two DataFrame columns and filled circles are used to represent each point. Scatter plot is useful for visualizing complex correlations between two variables.

## Examples

### Scatter Plots on Columns in a DataFrame

In the example below, we use the titanic dataset, to show a close to real-world use case of danfo.js

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <script src="https://cdn.jsdelivr.net/npm/danfojs@1.0.0/lib/bundle.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

          dfd.readCSV("https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/titanic.csv")
            .then(df => {
      
              df.plot("plot_div").scatter({
                config: { x: "Age", y: "Fare" }
              })
      
            }).catch(err => {
              console.log(err);
            })

    </script>
</body>

</html>
```

![](<../../.gitbook/assets/newplot-8- (1) (1).png>)

### More Examples

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <script src="https://cdn.jsdelivr.net/npm/danfojs@1.0.0/lib/bundle.js"></script>
    <title>Document</title>
</head>

<body>

    <div id="plot_div"></div>
    <script>

      dfd.readCSV("https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/titanic.csv")
        .then(df => {
  
          sub_df = df.loc({
            config: {
              columns: ["Age", "Fare", "Parch", "SibSp"]
            }
          })
          sub_df.plot("plot_div").scatter()
  
        }).catch(err => {
          console.log(err);
        })

    </script>
</body>

</html>
```

![](<../../.gitbook/assets/newplot (19).png>)

{% hint style="info" %}
To customize your plots, see the [Customize your plot page](configuring-your-plots.md)
{% endhint %}
