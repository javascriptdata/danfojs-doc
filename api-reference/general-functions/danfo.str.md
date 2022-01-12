---
description: Accessor object for String-like properties of Series values.
---

# danfo.Str

For example, in the following example, we convert a Series to an `Str` instance and apply a couple of **String** methods.&#x20;

{% tabs %}
{% tab title="Node" %}
```javascript
import { Str, Series } from "danfojs-node"

const sf = new Series(["Dog", "Cat", "Bird", "Fish", "ShArk", "tiGer"])
const sfStr = new Str(sf)

sfStr.toLowerCase().print()
sfStr.toUpperCase().print()
sfStr.join("Added", "-").print()
```
{% endtab %}
{% endtabs %}

```
// output
╔═══╤═══════╗
║ 0 │ dog   ║
╟───┼───────╢
║ 1 │ cat   ║
╟───┼───────╢
║ 2 │ bird  ║
╟───┼───────╢
║ 3 │ fish  ║
╟───┼───────╢
║ 4 │ shark ║
╟───┼───────╢
║ 5 │ tiger ║
╚═══╧═══════╝

╔═══╤═══════╗
║ 0 │ DOG   ║
╟───┼───────╢
║ 1 │ CAT   ║
╟───┼───────╢
║ 2 │ BIRD  ║
╟───┼───────╢
║ 3 │ FISH  ║
╟───┼───────╢
║ 4 │ SHARK ║
╟───┼───────╢
║ 5 │ TIGER ║
╚═══╧═══════╝
╔═══╤═════════════╗
║ 0 │ Dog-Added   ║
╟───┼─────────────╢
║ 1 │ Cat-Added   ║
╟───┼─────────────╢
║ 2 │ Bird-Added  ║
╟───┼─────────────╢
║ 3 │ Fish-Added  ║
╟───┼─────────────╢
║ 4 │ ShArk-Added ║
╟───┼─────────────╢
║ 5 │ tiGer-Added ║
╚═══╧═════════════╝

```
