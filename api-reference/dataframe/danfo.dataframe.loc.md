---
description: Access a group of rows and columns by label(s) or a boolean array.
---

# danfo.DataFrame.loc

`.loc[]` is primarily label based, but may also be used with a boolean array.

Allowed inputs are:

* A single label, e.g. `5` or `'a'`, \(note that `5` is interpreted as a _label_ of the index, and **never** as an integer position along the index\).
* A list or array of labels, e.g. `['a', 'b', 'c']`.
* A slice object with labels, e.g. `'a':'f'`.

**parameter:** kwargs\["type"\] = "loc"

            **return:** DataFrame without the removed index or column labels

