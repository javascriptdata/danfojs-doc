---
description: Return a fixed frequency Dates spread between start and end parameters.
---

# danfo.dateRange

danfo.**dateRange**(options)&#x20;

| Parameters  | Type   | Description                                                                                                                                                                                                                                                                                                                                                                                               |
| ----------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **options** | Object | <p>Includes any of the following:</p><p></p><p><strong>start</strong>: Left bound for generating dates.</p><p></p><p><strong>end</strong>: Right bound for generating dates.</p><p></p><p><strong>period</strong> : Number of periods to generate.</p><p></p><p><strong>offSet</strong>: Date range offset</p><p></p><p><strong>freq</strong>: Date range frequency. One of ["M","D","s","H","m","Y"]</p> |

## **Examples**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = new dfd.dateRange({"start":'1/1/2018', period:5, freq:'M'})
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
```
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

let data = new dfd.dateRange({ "start": '1/1/2018', period: 12, freq: 'Y' })
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
```
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
Datetime properties of Series or datetime-like columns in DataFrame can be accessed via accessors in the **dt** name space. See [Accessors](https://app.gitbook.com/@jsdata/s/danfojs/\~/drafts/-MEMaWwva1cjt8CxnG-b/api-reference/series#accessors)
{% endhint %}
