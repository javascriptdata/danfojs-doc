---
description: >-
  Return unique values of DataFrame along an axis. Uniques are returned in order
  of appearance. Set-based unique, therefore does NOT sort.
---

# DataFrame.unique

danfo.DataFrame.**unique**\(axis\) \[[source](https://github.com/opensource9ja/danfojs/blob/f84d7f53f2b0639e464f9483fb5cea969ad913d6/danfojs/src/core/frame.js#L1945)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| axis | Int |  0 for row axis, and 1 for column axis | 1 |

**Returns:**

       ****return **Object**

## **Examples**

### Return unique values along column axis \(axis=1\)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [{ "A": [-20, 30, 47.3, -20] },
            { "B": [34, -4, 5, 6] },
            { "C": [20, 20, 30, 30] },
            { "D": ["a", "b", "c", "c"] }]

let df = new dfd.DataFrame(data)
console.log(df.unique()) //defaults to axis 1
```
{% endtab %}

{% tab title="Browser" %}
```

```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
{
  A: [ -20, 30, 47.3 ],
  B: [ 34, -4, 5, 6 ],
  C: [ 20, 30 ],
  D: [ 'a', 'b', 'c' ]
}
```
{% endtab %}
{% endtabs %}

### Return unique values in row axis \(axis=0\)

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs")

let data = [{ "A": [-20, 30, 47.3, -20] },
            { "B": [34, -4, 5, 6] },
            { "C": [20, 20, 30, 30] },
            { "D": ["a", "b", "c", "c"] }]

let df = new dfd.DataFrame(data)
console.log(df.unique(axis=0));
```
{% endtab %}

{% tab title="Browser" %}
```

```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
{
  '0': [ -20, 34, 20, 'a' ],
  '1': [ 30, -4, 20, 'b' ],
  '2': [ 47.3, 5, 30, 'c' ],
  '3': [ -20, 6, 30, 'c' ]
}
```
{% endtab %}
{% endtabs %}

**Note:** To get the number of unique elements along an axis, use ****[DataFrame.nunique.](dataframe.nunique-1.md)

