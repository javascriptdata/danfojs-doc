---
description: >-
  Get difference between a dataframe and other. Accepts DataFrame, Series, number[] and number.
---

# DataFrame.diff

danfo.DataFrame.diff(other, option)&#x20;

| Parameters | Type                               | Description                                                                                                                                                                                            | Default                     |
| ---------- | ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------- |
| other      | DataFrame, Series, Array or Scalar | Object to calculate difference with                                                                                                                                                                    |                             |
| option     | Object                             | <p>{</p><p><strong>axis</strong>: 0 for column, 1 for row (default).</p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p><p>}</p> | { axis: 1, inplace: false } |

## **Examples**

### Difference with **previous row** of current DataFrame along default axis 1

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

const df_new = df.diff(1);

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
    <script src="https://cdn.jsdelivr.net/npm/danfojs@1.1.0/lib/bundle.min.js"></script>
  </head>

  <body>
    <script>
      const data = [
        [0, 2, 4],
        [10, 10, 10],
        [1, 2, 3],
      ];

      const df = new dfd.DataFrame(data);

      const df_new = df.diff(1);
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
║ 0          │ NaN               │ NaN               │ NaN               ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ 10                │ 8                 │ 6                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ -9                │ -8                │ -7                ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

```

{% endtab %}
{% endtabs %}

### Difference with **following row** of current DataFrame along default axis 1

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

const df_new = df.diff(-1);

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
    <script src="https://cdn.jsdelivr.net/npm/danfojs@1.1.0/lib/bundle.min.js"></script>
  </head>

  <body>
    <script>
      const data = [
        [0, 2, 4],
        [10, 10, 10],
        [1, 2, 3],
      ];

      const df = new dfd.DataFrame(data);

      const df_new = df.diff(-1);
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
║ 0          │ -10               │ -8                │ -6                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ 10                │ 8                 │ 6                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ NaN               │ NaN               │ NaN               ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

```

{% endtab %}
{% endtabs %}

### Difference with **Series** and DataFrame along axis 1

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

const df_new = df.diff(sf);

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
    <script src="https://cdn.jsdelivr.net/npm/danfojs@1.1.0/lib/bundle.min.js"></script>
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

      const df_new = df.diff(sf);
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
║ 1          │ 9                 │ 8                 │ 9                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ 0                 │ 0                 │ 2                 ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

```

{% endtab %}
{% endtabs %}

### Difference between DataFrame and **another** DataFrame

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
  [10, 5, 0],
]);

const df_new = original_df.diff(comparison_df);

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
    <script src="https://cdn.jsdelivr.net/npm/danfojs@1.1.0/lib/bundle.min.js"></script>
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
        [10, 5, 0],
      ]);

      const df_new = original_df.diff(comparison_df);
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
║ 0          │ 1                 │ 4                 │ 0                 ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ -7                │ 5                 │ 4                 ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

```

{% endtab %}
{% endtabs %}
