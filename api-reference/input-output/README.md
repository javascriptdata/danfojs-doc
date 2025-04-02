---
description: Functions for reading tabular/structured data into DataFrame/Series Objects
---

# Input/Output

## CSV

| \`\`                                |                                                          |
| ----------------------------------- | -------------------------------------------------------- |
| [`readCSV`](danfo.read_csv.md)     | Read a comma-separated values (csv) file into DataFrame. |
| [`read_excel`](danfo.read_excel.md) | Read an Excel values (xlsx) file into DataFrame.         |
| [`readJSON`](danfo.read_json.md)   | Read a JSON values (json) file into DataFrame.           |
| [toCSV](danfo.to_csv.md)           | Writes a DataFrame/Series to CSV file                    |
| [to_excel](danfo.to_excel.md)       | Writes a DataFrame/Series to Excel file                  |
| [toJSON](danfo.to_json.md)         | Writes a DataFrame/Series to JSON file                   |

Writing to `CSV` and `JSON` can also be done directly from DataFrame or Series objects (e.g. [`DataFrame.toCSV()`](../dataframe/dataframe.to_csv.md))
