---
description: Return a random sample of rows from DataFrame.
---

# DataFrame.sample

danfo.DataFrame.**sample**(num, seed) \[[source](https://github.com/opensource9ja/danfojs/blob/fe56860b0a303d218d60ba71dee6abf594401556/danfojs/src/core/frame.js#L314)]

| Parameters | Type | Description                                                                                                                        | Default |
| ---------- | ---- | ---------------------------------------------------------------------------------------------------------------------------------- | ------- |
| num        | Int  | The number of rows to return. Defaults to -1, which shuffles and return all rows.                                                  | -1      |
| seed       | int  | An integer specifying the random seed that will be used to create the distribution. Ensures reproducibility of generated samples.  | 1       |

**Returns:**

**       **return** {Promies} resolves to DataFrame**

****

## Sample a DataFrame randomly

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

async function load_data() {
  let data = {
    Name: ["Apples", "Mango", "Banana", "Pear"],
    Count: [21, 5, 30, 10],
    Price: [200, 300, 40, 250],
  };

  let df = new dfd.DataFrame(data);
  let s_df = await df.sample(2);
  s_df.print();
  
}

load_data()
```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ Name              │ Count             │ Price             ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ Apples            │ 21                │ 200               ║
╟───┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ Banana            │ 30                │ 40                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╝
```
{% endtab %}
{% endtabs %}

## Sample a DataFrame randomly with seed

By setting `seed` when using `sample`, you can ensure that the random sampling is reproducible. 

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

async function load_data() {
    let data = {
        Name: ["Apples", "Mango", "Banana", "Pear"],
        Count: [21, 5, 30, 10],
        Price: [200, 300, 40, 250],
    };

    let df = new dfd.DataFrame(data);
    let s_df = await df.sample(3, { seed: 2 });
    s_df.print();

}

load_data()
```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ Name              │ Count             │ Price             ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ Mango             │ 5                 │ 300               ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ Banana            │ 30                │ 40                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ Apples            │ 21                │ 200               ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝


```
{% endtab %}
{% endtabs %}
