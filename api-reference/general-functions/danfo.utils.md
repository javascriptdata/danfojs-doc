---
description: Utility class with useful methods
---

# danfo.Utils

The Utils class holds useful utility methods, mostly used internally in the Danfojs library.

For example, in the following example, we use the `inferDtype` function from the utils class.&#x20;

{% tabs %}
{% tab title="Node" %}
```javascript
import { Utils } from "danfojs-node"

const utils = new Utils()

const arr = [NaN, 2.1, 3.3, 2.09]
console.log(utils.inferDtype(arr))

//output
[ 'float32' ]
```
{% endtab %}
{% endtabs %}
