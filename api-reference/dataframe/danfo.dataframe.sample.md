---
description: Return a random sample of rows from DataFrame.
---

# DataFrame.sample

danfo.DataFrame.**sample**(num, options)

| Parameters | Type    | Description                                                                                                                                 | Default     |
| ---------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| num        | Integer | The number of rows to return. Defaults to 5, which shuffles and return all rows.                                                            | 5           |
| options    | Object  | **seed**: An integer specifying the random seed that will be used to create the distribution. Ensures reproducibility of generated samples. | { seed: 1 } |

## Sample a DataFrame randomly

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

async function sample_data() {
    let data = {
        Name: ["Apples", "Mango", "Banana", "Pear"],
        Count: [21, 5, 30, 10],
        Price: [200, 300, 40, 250],
    };

    let df = new dfd.DataFrame(data);
    let s_df = await df.sample(2);
    s_df.print();

}

sample_data()
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
