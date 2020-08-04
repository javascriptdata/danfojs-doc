---
description: >-
  Reads a comma-separated values (CSV) file into DataFrame. Also supports
  iterating or breaking of file into chunks.
---

# danfo.read\_csv

danfo.**read\_csv**\(source, chunk\) [\[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/io/reader.js#L21)\]

**Parameters**: 

_**source**_: \(str, path or URL \). Any valid string path is acceptable. The string could be a URL. Valid URL schemes include http, ftp, s3, gs, and file. For local file path, it should be prefixed with " **file://**", for example, "**file:///home/path/to/table.csv**".

**chunk:** \(int, optional\). The number of rows of file to read. Useful for reading pieces of large files.

### Example

The **read\_csv** method can read csv file from local disk, or over the internet. If the file is to be read from a local disk in Node environment, you have to prefix the full path name with a "**file://**" prefix. For instance, to read a csv file at the path **/home/Desktop/user\_names.csv**, you can do the following:

Install danfo, create a file called app.js, download the titanic dataset from [here](https://web.stanford.edu/class/archive/cs/cs109/cs109.1166/stuff/titanic.csv), and run the following: 

{% tabs %}
{% tab title="Node.js" %}
```javascript
const dfd = require("danfojs")

dfd.read_csv("file:///home/Desktop/titanic.csv")
  .then(df => {
  
   df.head().print()

  })
```
{% endtab %}

{% tab title="Browser" %}
```

```
{% endtab %}
{% endtabs %}

Output**:**

![Output of head function in the console](../../.gitbook/assets/image%20%281%29.png)

**Reading Large Files**

For extremely large files, that cannot be fit in memory at once, you can read the top portion in chunks. For instance, this [dataset](http://eforexcel.com/wp/wp-content/uploads/2017/07/1500000%20Sales%20Records.7z) has over 1.5 million rows and will throw a memory error if you try to load everything at once. To read these type of files, you can load them in chunks using the chunks parameter in **read\_csv**

Download the Titanic dataset from [here](http://eforexcel.com/wp/wp-content/uploads/2017/07/1500000%20Sales%20Records.7z)

{% tabs %}
{% tab title="JavaScript" %}
```javascript
const dfd = require("danfojs")

//read the first 10000 rows
dfd.read_csv("file:///home/Desktop/titanic.csv", chunk=10000)
  .then(df => {
  
   df.tail().print()

  })
```
{% endtab %}

{% tab title="Browser" %}
```

```
{% endtab %}
{% endtabs %}

Output:

![The last 5 rows of the big dataset](../../.gitbook/assets/image%20%283%29.png)

