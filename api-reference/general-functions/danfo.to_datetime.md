---
description: Convert Object to datetime format
---

# danfo.to\_datetime

danfo.**to\_datetime**\(kwargs\) \[[source](https://github.com/opensource9ja/danfojs/blob/fe56860b0a303d218d60ba71dee6abf594401556/danfojs/src/core/frame.js#L254)\]

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameters</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Default</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>kwargs</b>
      </td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">
        <p>{</p>
        <p><b>data</b>: Array | Series, the object to convert.</p>
        <p><b>format</b>: The strftime to parse time, eg &quot;%Y-m-d%&quot;, &quot;%m-d-Y%&quot;,
          and &quot;%m-d-Y H%M%S%&quot;</p>
        <p>}</p>
      </td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

**Returns:**

       ****return **DataFrame**

## **Examples**

### **Convert Series to Dummy codes**

{% tabs %}
{% tab title="Node" %}
```javascript
let data = new dfd.date_range({"start":'1/1/2018',period:12, freq:'M'})
let sf = new dfd.Series(data)
let dt = dfd.to_datetime({data:sf})

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
```text
//Int representation for month
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 0                    ║
╟───┼──────────────────────╢
║ 1 │ 1                    ║
╟───┼──────────────────────╢
║ 2 │ 2                    ║
╟───┼──────────────────────╢
║ 3 │ 3                    ║
╟───┼──────────────────────╢
║ 4 │ 4                    ║
╚═══╧══════════════════════╝

//string representation for month
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ Jan                  ║
╟───┼──────────────────────╢
║ 1 │ Feb                  ║
╟───┼──────────────────────╢
║ 2 │ Mar                  ║
╟───┼──────────────────────╢
║ 3 │ Apr                  ║
╟───┼──────────────────────╢
║ 4 │ May                  ║
╚═══╧══════════════════════╝

//string representation for day of the week
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ Mon                  ║
╟───┼──────────────────────╢
║ 1 │ Thu                  ║
╟───┼──────────────────────╢
║ 2 │ Thu                  ║
╟───┼──────────────────────╢
║ 3 │ Sun                  ║
╟───┼──────────────────────╢
║ 4 │ Tue                  ║
╚═══╧══════════════════════╝

//Int representation for day of the week
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 1                    ║
╟───┼──────────────────────╢
║ 1 │ 4                    ║
╟───┼──────────────────────╢
║ 2 │ 4                    ║
╟───┼──────────────────────╢
║ 3 │ 0                    ║
╟───┼──────────────────────╢
║ 4 │ 2                    ║
╚═══╧══════════════════════╝
//Hour of the day

╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 0                    ║
╟───┼──────────────────────╢
║ 1 │ 0                    ║
╟───┼──────────────────────╢
║ 2 │ 0                    ║
╟───┼──────────────────────╢
║ 3 │ 0                    ║
╟───┼──────────────────────╢
║ 4 │ 0                    ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
datetime properties of Series or datetime-like columns in DataFrame can be accessed via accessors in the **dt** name space. See  [Accessors](https://app.gitbook.com/@jsdata/s/danfojs/~/drafts/-MEMaWwva1cjt8CxnG-b/api-reference/series#accessors)
{% endhint %}

