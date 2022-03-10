---
description: >-
  Get percent difference between a dataframe and other. Accepts DataFrame, Series, number[] and number.
---

# DataFrame.pctChange

danfo.DataFrame.pctChange(other, option)&#x20;

| Parameters | Type                               | Description                                                                                                                                                                                            | Default                     |
| ---------- | ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------- |
| other      | DataFrame, Series, Array or Scalar | Object to calculate difference with                                                                                                                                                                    |                             |
| option     | Object                             | <p>{</p><p><strong>axis</strong>: 0 for column, 1 for row (default).</p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p><p>}</p> | { axis: 1, inplace: false } |

## **Examples**

### Percent difference with **previous row** of current DataFrame along default axis 1

{% tabs %}
{% tab title="Node" %}

```javascript
import * as dfd from "danfojs";

const data = [[90], [900], [900]];

const df = new dfd.DataFrame(data);

const df_new = df.pctChange(1);

df_new.print();
```

{% endtab %}

{% tab title="Browser" %}

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <script src="https://cdn.jsdelivr.net/npm/danfojs@1.0.2/lib/bundle.min.js"></script>
  </head>

  <body>
    <script>
      const data = [[90, 900, 900]];

      const df = new dfd.DataFrame(data);

      const df_new = df.pctChange(1);
    </script>
  </body>
</html>
```

{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}

```
╔════════════╤═══════════════════╗
║            │ Col1              ║
╟────────────┼───────────────────╢
║ 0          │ NaN               ║
╟────────────┼───────────────────╢
║ 1          │ 9                 ║
╟────────────┼───────────────────╢
║ 2          │ 0                 ║
╚════════════╧═══════════════════╝

```

{% endtab %}
{% endtabs %}

### Percentage difference with **following row** of current DataFrame along default axis 1

{% tabs %}
{% tab title="Node" %}

```javascript
import * as dfd from "danfojs";

const data = [
  [0, 5, 15],
  [10, 10, 10],
  [1, 2, 5],
];

const df = new dfd.DataFrame(data);

const df_new = df.pctChange(-1);

df_new.print();
```

{% endtab %}

{% tab title="Browser" %}

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <script src="https://cdn.jsdelivr.net/npm/danfojs@1.0.2/lib/bundle.min.js"></script>
  </head>

  <body>
    <script>
      const data = [
        [0, 5, 15],
        [10, 10, 10],
        [1, 2, 5],
      ];

      const df = new dfd.DataFrame(data);

      const df_new = df.pctChange(-1);
    </script>
  </body>
</html>
```

{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ Col1              │ Col2              │ Col3              ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ -1                │ -0.5              │ 0.5               ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ 9                 │ 4                 │ 1                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ NaN               │ NaN               │ NaN               ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

```

{% endtab %}
{% endtabs %}

### Percentage difference with **Series** and DataFrame along axis 1

{% tabs %}
{% tab title="Node" %}

```javascript
import * as dfd from "danfojs";

const data = [
  [0, 2, 4],
  [10, 10, 10],
  [1, 2, 3],
];

const df = new dfd.DataFrame(data);

const sf = new dfd.Series([1, 2, 1]);

const df_new = df.pctChange(sf);

df_new.print();
```

{% endtab %}

{% tab title="Browser" %}

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <script src="https://cdn.jsdelivr.net/npm/danfojs@1.0.2/lib/bundle.min.js"></script>
  </head>

  <body>
    <script>
      const data = [
        [0, 2, 4],
        [10, 10, 10],
        [1, 2, 3],
      ];

      const df = new dfd.DataFrame(data);

      const sf = new dfd.Series([1, 2, 1]);

      const df_new = df.pctChange(sf);
    </script>
  </body>
</html>
```

{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ Col1              │ Col2              │ Col3              ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ -1                │ 0                 │ 3                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ 9                 │ 4                 │ 9                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ 0                 │ 0                 │ 2                 ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

```

{% endtab %}
{% endtabs %}

### Percentage difference between DataFrame and **another** DataFrame

{% tabs %}
{% tab title="Node" %}

```javascript
import * as dfd from "danfojs";

const data = [
  [0, 2, 4],
  [3, 10, 4],
];

const original_df = new dfd.DataFrame(data);

const comparison_df = new dfd.DataFrame([
  [-1, -2, 4],
  [6, 5, 0],
]);

const df_new = original_df.pctChange(comparison_df);

df_new.print();
```

{% endtab %}

{% tab title="Browser" %}

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <script src="https://cdn.jsdelivr.net/npm/danfojs@1.0.2/lib/bundle.min.js"></script>
  </head>

  <body>
    <script>
      const data = [
        [0, 2, 4],
        [3, 10, 4],
      ];

      const original_df = new dfd.DataFrame(data);

      const comparison_df = new dfd.DataFrame([
        [-1, -2, 4],
        [6, 5, 0],
      ]);

      const df_new = original_df.pctChange(comparison_df);
    </script>
  </body>
</html>
```

{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}

```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ Col1              │ Col2              │ Col3              ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ -1                │ -2                │ 0                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ -0.5              │ 1                 │ -1                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

```

{% endtab %}
{% endtabs %}
