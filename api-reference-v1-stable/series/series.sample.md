---
description: Return a random sample of items from an axis of object.
---

# Series.sample

> danfo.Series.sample(num)   \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L98)]

| Parameters | Type   | Description                                                                                                                                  | Default                        |
| ---------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------ |
| num        | Int    | The number of rows to return.                                                                                                                |                                |
| options    | Object | **seed**: An integer specifying the random seed that will be used to create the distribution. Ensures reproducibility of generated samples.  | <p>{</p><p>seed: 1</p><p>}</p> |

**Returns:**

&#x20;      ****       return **{Promies} resolves to Series**

**Example**

```javascript
const dfd = require("danfojs-node")

async function load_data() {
  let data1 = [1, 2, 3, 4, 5, 620, 30, 40, 39, 89, 78];
  let sf1 = new dfd.Series(data1);
  let sample = await sf1.sample(5)
  sample.print()
  
}
load_data()
```

{% tabs %}
{% tab title="Output" %}
```javascript
╔═══╤════╗
║ 2 │ 3  ║
╟───┼────╢
║ 4 │ 5  ║
╟───┼────╢
║ 0 │ 1  ║
╟───┼────╢
║ 7 │ 40 ║
╟───┼────╢
║ 6 │ 30 ║
╚═══╧════╝
```
{% endtab %}
{% endtabs %}

### Specify a seed when sampling

```javascript
const dfd = require("danfojs-node")

async function load_data() {
    let data1 = [1, 2, 3, 4, 5, 620, 30, 40, 39, 89, 78];
    let sf1 = new dfd.Series(data1);
    let sample = await sf1.sample(5, { seed: 2 })
    sample.print()

}
load_data()

```
