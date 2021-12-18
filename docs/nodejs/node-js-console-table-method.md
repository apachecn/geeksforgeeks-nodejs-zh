# Node.js console.table()方法

> 原文:[https://www.geeksforgeeks.org/node-js-console-table-method/](https://www.geeksforgeeks.org/node-js-console-table-method/)

**console.table()方法**是控制台模块的内置应用编程接口，用于将由其参数构建的表打印到控制台中。

**语法:**

```
console.table(data, properties);
```

**参数:**该方法接受两个参数，如上所述，如下所述:

1.  **Data:** Table data. An array of data for each row, containing the values of each column of that particular row.
2.  **Attribute:** Specify the attribute of the construction table.

**返回值:**这个方法不返回任何东西，只打印构造好的表并记录下来。如果它无法将参数解析到表中，那么它只是记录参数。

下面的例子说明了在 Node.js 中使用 console.table()方法

**示例 1:** **文件名:app.js**

```
// Node.js program to demonstrate the   
// console.table() method

// Accessing console module
const console = require('console');

// Calling console.table() 
// without construction rule
console.table([
    { a: 1, b: 2 }, 
    { a: 3, b: 7, c: 'y' }
]);

// With construction rule
console.table([
    { a: 1, b: 2 }, 
    { a: 3, b: 7, c: 'y' }],
    ["a", "b"]
);
```

使用以下命令运行 app.js 文件:

```
node app.js
```

**输出:**

```
┌─────────┬───┬───┬─────┐
│ (index) │ a │ b │ c   │
├─────────┼───┼───┼─────┤
│    0    │ 1 │ 2 │     │
│    1    │ 3 │ 7 │ 'y' │
└─────────┴───┴───┴─────┘

┌─────────┬───┬───┐
│ (index) │ a │ b │
├─────────┼───┼───┤
│    0    │ 1 │ 2 │
│    1    │ 3 │ 7 │
└─────────┴───┴───┘

```

**示例 2:** **文件名:app.js**

```
// Node.js program to demonstrate the   
// console.table() method

// Accessing console module
const console = require('console');

// Calling console.table() 
// fails to parse, so simply 
// print the argument
console.table("arg");

// Blank table
console.table([]);
```

使用以下命令运行 app.js 文件:

```
node app.js
```

**输出:**

```
arg
┌─────────┐
│ (index) │
├─────────┤
└─────────┘

```

**注意:**以上程序将使用 node filename.js 命令编译运行。

**参考:**[https://nodejs . org/API/console . html # console _ console _ table _ tabulardata _ properties](https://nodejs.org/api/console.html#console_console_table_tabulardata_properties)