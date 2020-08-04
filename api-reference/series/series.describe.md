---
description: >-
  Generate descriptive statistics. Descriptive statistics include those that
  summarize the central tendency, dispersion and shape of a dataset’s
  distribution, excluding NaN values
---

# Series.describe

> danfo.Series.describe\(\) \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L583)\]

**Parameters:** No parameter

**return:** Series

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [1,2,3,4,5,6]
let sf = new dfd.Series(data)
sf.describe().print()
```
{% endtab %}

{% tab title="Browser" %}
```

```
{% endtab %}
{% endtabs %}

**OUTPUT:**

![](../../.gitbook/assets/series_describe.png)

