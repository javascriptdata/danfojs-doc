---
description: Accessor object for date time properties of the Series values.
---

# danfo.Dt

For example, in the following example, we convert a Series to an `Dt` instance and apply a couple of **DateTime** methods.&#x20;

{% tabs %}
{% tab title="Node" %}
```javascript
import { Dt, Series } from "danfojs-node-nightly"

const sf = new Series(["1/1/2000", "1/2/2000", "2/3/2000", "1/4/2000", "4/5/2000"])
const dtS = new Dt(sf)

dtS.dayOfWeekName().print()
dtS.monthName().print()
```
{% endtab %}
{% endtabs %}

```
// output
╔═══╤═══════════╗
║ 0 │ Saturday  ║
╟───┼───────────╢
║ 1 │ Sunday    ║
╟───┼───────────╢
║ 2 │ Thursday  ║
╟───┼───────────╢
║ 3 │ Tuesday   ║
╟───┼───────────╢
║ 4 │ Wednesday ║
╚═══╧═══════════╝

╔═══╤══════════╗
║ 0 │ January  ║
╟───┼──────────╢
║ 1 │ January  ║
╟───┼──────────╢
║ 2 │ February ║
╟───┼──────────╢
║ 3 │ January  ║
╟───┼──────────╢
║ 4 │ April    ║
╚═══╧══════════╝

```
