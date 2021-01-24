---
description: Return a fixed frequency Dates spread between start and end parameters.
---

# danfo.date\_range

danfo.**date\_range**\(kwargs\) \[[source](https://github.com/opensource9ja/danfojs/blob/fe56860b0a303d218d60ba71dee6abf594401556/danfojs/src/core/frame.js#L254)\]

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
        <p><b>start</b>: str or datetime-like. Left bound for generating dates.</p>
        <p><b>end</b>: str or datetime-like. Right bound for generating dates.</p>
        <p><b>period</b> : int. Number of periods to generate.</p>
        <p><b>freq</b>: str or DateOffset, one of [&quot;M&quot;,&quot;D&quot;,&quot;s&quot;,&quot;H&quot;,&quot;m&quot;,&quot;Y&quot;].</p>
        <p>}</p>
      </td>
      <td style="text-align:left">{<b>freq:</b> &apos;D&apos;}</td>
    </tr>
  </tbody>
</table>

**Returns:**

       ****return **DataFrame**

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = new dfd.date_range({"start":'1/1/2018',period:5, freq:'M'})
console.log(data);
```
{% endtab %}

{% tab title="Browser" %}
```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <!--danfojs CDN -->
    <script src="https://cdn.jsdelivr.net/gh/opensource9ja/danfojs@latest/lib/bundle.js"></script>
    <title>Document</title>
</head>

<body>

    <script>

        let data = new dfd.date_range({"start":'1/1/2018',period:5, freq:'M'})
        console.log(data);
         
    </script>
</body>

</html>

```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```text
[
  '1/1/2018, 12:00:00 AM',
  '2/1/2018, 12:00:00 AM',
  '3/1/2018, 12:00:00 AM',
  '4/1/2018, 12:00:00 AM',
  '5/1/2018, 12:00:00 AM'
]
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = new dfd.date_range({"start":'1/1/2018',period:12, freq:'Y'})
console.log(data);
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
[
  '1/1/2018, 12:00:00 AM',
  '1/1/2019, 12:00:00 AM',
  '1/1/2020, 12:00:00 AM',
  '1/1/2021, 12:00:00 AM',
  '1/1/2022, 12:00:00 AM',
  '1/1/2023, 12:00:00 AM',
  '1/1/2024, 12:00:00 AM',
  '1/1/2025, 12:00:00 AM',
  '1/1/2026, 12:00:00 AM',
  '1/1/2027, 12:00:00 AM',
  '1/1/2028, 12:00:00 AM',
  '1/1/2029, 12:00:00 AM'
]
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
datetime properties of Series or datetime-like columns in DataFrame can be accessed via accessors in the **dt** name space. See  [Accessors](https://app.gitbook.com/@jsdata/s/danfojs/~/drafts/-MEMaWwva1cjt8CxnG-b/api-reference/series#accessors)
{% endhint %}

