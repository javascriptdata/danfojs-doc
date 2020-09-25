# Series.append

danfo.Series.**append**\(val, inplace\) \[[source](https://github.com/opensource9ja/danfojs/blob/2696f1d8420dd364464aae7c5c175c6cd0ef4c93/danfojs/src/core/frame.js#L2059)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| val | Array \| Series | Object to append |  |
| inplace | Boolean | Whether to perform operation inplace or not | false |

**Returns:**

       ****return **Series**

## **Examples**

### **Append Series to Series**

{% tabs %}
{% tab title="Node" %}
```javascript
let sf1 = new dfd.Series([1, 2, 3, 4])
let sf2 = new dfd.Series(["a", "b", "c"], {index: ['f1', 'f2', 'f3']})

new_sf = sf1.append(sf2)
new_sf.print()
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
╔════╤══════════════════════╗
║    │ 0                    ║
╟────┼──────────────────────╢
║ 0  │ 1                    ║
╟────┼──────────────────────╢
║ 1  │ 2                    ║
╟────┼──────────────────────╢
║ 2  │ 3                    ║
╟────┼──────────────────────╢
║ 3  │ 4                    ║
╟────┼──────────────────────╢
║ f1 │ a                    ║
╟────┼──────────────────────╢
║ f2 │ b                    ║
╟────┼──────────────────────╢
║ f3 │ c                    ║
╚════╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

\*\*\*\*

### **Append Array to Series**

{% tabs %}
{% tab title="Node" %}
```javascript
let sf1 = new dfd.Series([1, 2, 3, 4])
let arr = ['f1', 'f2', 'f3']

new_sf = sf1.append(arr)
new_sf.print()

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
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 1                    ║
╟───┼──────────────────────╢
║ 1 │ 2                    ║
╟───┼──────────────────────╢
║ 2 │ 3                    ║
╟───┼──────────────────────╢
║ 3 │ 4                    ║
╟───┼──────────────────────╢
║ 0 │ f1                   ║
╟───┼──────────────────────╢
║ 1 │ f2                   ║
╟───┼──────────────────────╢
║ 2 │ f3                   ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

