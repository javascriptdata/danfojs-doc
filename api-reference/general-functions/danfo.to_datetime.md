---
description: Converts an array of Date strings to Date object.
---

# danfo.toDateTime

danfo.**toDateTime**(data)&#x20;

| Parameters | Type          | Description     | Default                                           |
| ---------- | ------------- | --------------- | ------------------------------------------------- |
| **data**   | Array, Series | **data**: Array | Series with Date strings to convert to Date time. |

## **Examples**

In the following example, we convert a **Series** of Date strings to DateTime objects, so we can call various Date methods on them.&#x20;

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require('danfojs-node')

let data = new dateRange({ "start": '1/1/2018', period: 12, freq: 'M' })
let sf = new Series(data)
sf.print()

let dt = toDateTime(data)
dt.dayOfMonth().print()
dt.dayOfWeekName().print()
dt.hours().print()
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
╔═══╤════════════════════════╗
║ 0 │ 1/1/2018, 12:00:00 AM  ║
╟───┼────────────────────────╢
║ 1 │ 2/1/2018, 12:00:00 AM  ║
╟───┼────────────────────────╢
║ 2 │ 3/1/2018, 12:00:00 AM  ║
╟───┼────────────────────────╢
║ 3 │ 4/1/2018, 12:00:00 AM  ║
╟───┼────────────────────────╢
║ 4 │ 5/1/2018, 12:00:00 AM  ║
╟───┼────────────────────────╢
║ 5 │ 6/1/2018, 12:00:00 AM  ║
╟───┼────────────────────────╢
║ 6 │ 7/1/2018, 12:00:00 AM  ║
╟───┼────────────────────────╢
║ 7 │ 8/1/2018, 12:00:00 AM  ║
╟───┼────────────────────────╢
║ 8 │ 9/1/2018, 12:00:00 AM  ║
╟───┼────────────────────────╢
║ 9 │ 10/1/2018, 12:00:00 AM ║
╚═══╧════════════════════════╝

╔═══╤═══╗
║ 0 │ 1 ║
╟───┼───╢
║ 1 │ 1 ║
╟───┼───╢
║ 2 │ 1 ║
╟───┼───╢
║ 3 │ 1 ║
╟───┼───╢
║ 4 │ 1 ║
╟───┼───╢
║ 5 │ 1 ║
╟───┼───╢
║ 6 │ 1 ║
╟───┼───╢
║ 7 │ 1 ║
╟───┼───╢
║ 8 │ 1 ║
╟───┼───╢
║ 9 │ 1 ║
╚═══╧═══╝

╔═══╤═══════════╗
║ 0 │ Monday    ║
╟───┼───────────╢
║ 1 │ Thursday  ║
╟───┼───────────╢
║ 2 │ Thursday  ║
╟───┼───────────╢
║ 3 │ Sunday    ║
╟───┼───────────╢
║ 4 │ Tuesday   ║
╟───┼───────────╢
║ 5 │ Friday    ║
╟───┼───────────╢
║ 6 │ Sunday    ║
╟───┼───────────╢
║ 7 │ Wednesday ║
╟───┼───────────╢
║ 8 │ Saturday  ║
╟───┼───────────╢
║ 9 │ Monday    ║
╚═══╧═══════════╝

╔═══╤═══╗
║ 0 │ 0 ║
╟───┼───╢
║ 1 │ 0 ║
╟───┼───╢
║ 2 │ 0 ║
╟───┼───╢
║ 3 │ 0 ║
╟───┼───╢
║ 4 │ 0 ║
╟───┼───╢
║ 5 │ 0 ║
╟───┼───╢
║ 6 │ 0 ║
╟───┼───╢
║ 7 │ 0 ║
╟───┼───╢
║ 8 │ 0 ║
╟───┼───╢
║ 9 │ 0 ║
╚═══╧═══╝

```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Date time properties of Series or datetime-like columns in DataFrame can be accessed via accessors in the **dt** name-space. See [Accessors](https://app.gitbook.com/@jsdata/s/danfojs/\~/drafts/-MEMaWwva1cjt8CxnG-b/api-reference/series#accessors)
{% endhint %}
