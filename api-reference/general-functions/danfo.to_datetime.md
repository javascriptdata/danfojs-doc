---
description: Converts an array of Date time string to Date object.
---

# danfo.toDateTime

danfo.**toDateTime**(data) \[[source](https://github.com/opensource9ja/danfojs/blob/fe56860b0a303d218d60ba71dee6abf594401556/danfojs/src/core/frame.js#L254)]

| Parameters | Type          | Description                                                                                                       | Default |
| ---------- | ------------- | ----------------------------------------------------------------------------------------------------------------- | ------- |
| **data**   | Array, Series | <p><strong>data</strong>:  Array | Series with Date strings to convert to Date time. </p><p><strong></strong></p> |         |

**Returns:**

&#x20;      ****       return **DataFrame**

## **Examples**

Converts a **Series** of Date strings to Date time and get time properties

{% tabs %}
{% tab title="Node" %}
```javascript
let data = new dfd.date_range({"start":'1/1/2018',period:12, freq:'M'})
let sf = new dfd.Series(data)
sf.print()

let dt = dfd.toDateTime(data)

dt.month().print()
dt.month_name().print()
dt.weekdays().print()
dt.day().print()
dt.seconds().print()
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
  0
0	1/1/2018, 12:00:00 AM
1	2/1/2018, 12:00:00 AM
2	3/1/2018, 12:00:00 AM
3	4/1/2018, 12:00:00 AM
4	5/1/2018, 12:00:00 AM
5	6/1/2018, 12:00:00 AM
6	7/1/2018, 12:00:00 AM
7	8/1/2018, 12:00:00 AM
8	9/1/2018, 12:00:00 AM
9	10/1/2018, 12:00:00 AM
10	11/1/2018, 12:00:00 AM
11	12/1/2018, 12:00:00 AM

//Int representation for month
	0
0	0
1	1
2	2
3	3
4	4
5	5
6	6
7	7
8	8
9	9
10	10
11	11

//string representation for month
0
0	Jan
1	Feb
2	Mar
3	Apr
4	May
5	Jun
6	Jul
7	Aug
8	Sep
9	Oct
10	Nov
11	Dec

//string representation for day of the week
0
0	Mon
1	Thur
2	Thur
3	Sun
4	Tue
5	Fri
6	Sun
7	Wed
8	Sat
9	Mon
10	Thur
11	Sat

0
0	1
1	4
2	4
3	0
4	2
5	5
6	0
7	3
8	6
9	1
10	4
11	6

//Hour of the day
0
0	0
1	0
2	0
3	0
4	0
5	0
6	0
7	0
8	0
9	0
10	0
11	0

```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Date time properties of Series or datetime-like columns in DataFrame can be accessed via accessors in the **dt** name-space. See  [Accessors](https://app.gitbook.com/@jsdata/s/danfojs/\~/drafts/-MEMaWwva1cjt8CxnG-b/api-reference/series#accessors)
{% endhint %}
