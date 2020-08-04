# danfo.read\_json

> danfo.**read\_json**\(source, chunk\) [\[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/io/reader.js#L38)\]

| **Parameters** | Type | Description | Default |
| :--- | :--- | :--- | :--- |
| _**source**_: | str, path or URL  | Any valid string path is acceptable. The string could be a URL. Valid URL schemes include http, ftp, s3, gs, and file. For local file path, it should be prefixed with " **file://**", for example, "**file:///home/path/to/table.csv**". |  |
| **chunk**: |  int, optional | The number of rows of file to read. Useful for reading pieces of large files. |  |

**Returns:**

     ****_**Promise**_. Resolves to DataFrame

### Example

The **read\_csv** method can read csv file from local disk, or over the internet. If the file is to be read from a local disk in Node environment, you have to prefix the full path name with a "**file://**" prefix. For instance, to read a csv file at the path **/home/Desktop/user\_names.csv**, you can do the following:

Install danfo, create a file called app.js, download the titanic dataset from [here](https://web.stanford.edu/class/archive/cs/cs109/cs109.1166/stuff/titanic.csv), and run the following: 

