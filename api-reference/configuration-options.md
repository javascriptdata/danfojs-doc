---
description: >-
  This section describes all user configurable options available on
  DataFrame/Series creation.
---

# Configuration Options

On DataFrame/Series creation, a config object can be passed along to configure some internal properties of the created object. The following list shows what options are available and what they do. 

| Parameter | Description |
| :--- | :--- |
| tableDisplayConfig | **Object**, General table display options. Because we use the table package under the hood to display a table in the console, all [table display configurations](https://www.npmjs.com/package/table) are supported.  |
| tableMaxRow | **Number**, the total number of rows to display in the console when the **print** function is called. Defaults to 10 |
| dtypeTestLim | **Number**, the total number of values to test when inferring data type. Defaults to 10 |
| lowMemoryMode | **Boolean**, whether to use minimal memory or not. Defaults to false.  **Note:** There's a slight decrease in speed when low memory mode is set to true.  |

> See an example of creating DataFrame [in low memory mode](dataframe/creating-a-dataframe.md#creating-a-dataframe-and-specifying-memory-mode)

## Examples of setting configs

### Add a DataFrame header

```javascript
 const data = {
                "Name": ["Apples", "Mango", "Banana", "Pear"],
                "Count": [21, 5, 30, 10],
                "Price": [200, 300, 40, 250]
            };
const df = new DataFrame(data, {
    config: {
        tableDisplayConfig: {
            header: {
                alignment: 'center',
                content: 'THE HEADER\nThis is the table about something',
            },
        },
    }
});
df.print()
```

```javascript
╔════════════════════════════════════════════════════════════════════════╗
║                               THE HEADER                               ║
║                   This is the table about something                    ║
╟────────────┬───────────────────┬───────────────────┬───────────────────╢
║            │ Name              │ Count             │ Price             ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ Apples            │ 21                │ 200               ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1          │ Mango             │ 5                 │ 300               ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2          │ Banana            │ 30                │ 40                ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3          │ Pear              │ 10                │ 250               ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

### Configure column size and display format of DataFrame

```javascript
const data = {
    "Name": ["Apples", "Mango", "Banana", "Pear"],
    "Count": [21, 5, 30, 10],
    "Price": [200, 300, 40, 250]
};
const df = new DataFrame(data, {
    config: {
        tableDisplayConfig: {
            header: {
                alignment: 'center',
                content: 'THE HEADER\nThis is the table about something',
            },
            columns: [
                { alignment: 'left' },
                { alignment: 'center', width: 20 },
                { alignment: 'right' },
                { alignment: 'justify' }
            ],
        },
    }
});
df.print()
```

```javascript
╔══════════════════════════════════════════╗
║                THE HEADER                ║
║    This is the table about something     ║
╟───┬──────────────────────┬───────┬───────╢
║   │         Name         │ Count │ Price ║
╟───┼──────────────────────┼───────┼───────╢
║ 0 │        Apples        │    21 │ 200   ║
╟───┼──────────────────────┼───────┼───────╢
║ 1 │        Mango         │     5 │ 300   ║
╟───┼──────────────────────┼───────┼───────╢
║ 2 │        Banana        │    30 │ 40    ║
╟───┼──────────────────────┼───────┼───────╢
║ 3 │         Pear         │    10 │ 250   ║
╚═══╧══════════════════════╧═══════╧═══════╝
```

### Configure the number of rows displayed when **print** is called

```javascript
const data = {
    "Name": ["Apples", "Mango", "Banana", "Pear"],
    "Count": [21, 5, 30, 10],
    "Price": [200, 300, 40, 250],

};
const df = new DataFrame(data, {
    config: {
        tableMaxColInConsole: 6,
        tableMaxRow: 1
    }
});
df.print()
```

```text
╔════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║            │ Name              │ Count             │ Price             ║
╟────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0          │ Apples            │ 21                │ 200               ║
╚════════════╧═══════════════════╧═══════════════════╧═══════════════════╝
```

