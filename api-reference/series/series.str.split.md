---
description: >-
  Split string around a given separator/delimiter. The array of strings are then
  converted to a string.
---

# Series.str.split

> danfo.Series.str.**split**\(splitVal\) \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/strings.js#L250)\]

| Parameters | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| splitVal | String | separator or delimiter used to split the string  | " " |

**Returns**

                      return **Series**

**Examples**

Split the string value in the Series by space and obtain the Series values

{% tabs %}
{% tab title="JavaScript" %}
```javascript
const dfd = require("danfojs-node")

let data = ["king of the music","the lamba queen","I love the hat"]
let sf = new dfd.Series(data)
console.log(sf.str.split().values)
```
{% endtab %}

{% tab title="Browser" %}
```

```
{% endtab %}
{% endtabs %}

**OUTPUT:**     `[ 'king,of,the,music', 'the,lamba,queen', 'I,love,the,hat' ]`

{% tabs %}
{% tab title="JavaScript" %}
```javascript
const dfd = require("danfojs-node")

let data = ["king_of_the_music","the_lamba_queen","I_love_the_hat"]
let sf = new dfd.Series(data)
sf.str.split("_").print()
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
║ 0 │ king,of,the,music    ║
╟───┼──────────────────────╢
║ 1 │ the,lamba,queen      ║
╟───┼──────────────────────╢
║ 2 │ I,love,the,hat       ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

