# node . js console . group collapsed()方法

> 原文:[https://www . geesforgeks . org/node-js-console-group collapsed-method/](https://www.geeksforgeeks.org/node-js-console-groupcollapsed-method/)

**console.groupCollapsed()方法**内置于 **console** 模块中，用于折叠分组内容，直到调用 console.groupEnd()方法。它启动折叠的组，可以用 groupEnd()方法结束。

**语法:**

```
console.groupCollapsed([label]);
```

**参数:**该方法只接受一个参数，如上所述，如下所述:

**标签:**您在控制台上分组的组的标签。这是一个可选参数。

**返回值:**不返回值。

下面的例子说明了在 Node.js 中使用 **console.groupCollapsed()** 方法。

**例 1:**

**文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// console.groupCollapsed() method
// This code example demonstrate the
// method without parameter

// Accessing console module
const console = require('console');

console.log("GeeksforGeeks (Outside)")
console.log();

// Creating first group calling
// console.groupCollapsed() method
console.groupCollapsed();

// Printing First line of Group
console.log("GeeksforGeeks (1)");

// Printing Second line of Group
console.log("GeeksforGeeks (2)");

// End the group (It is used to end the
// group for more understanding the
// group method)
console.groupEnd();
console.log();
```

使用以下命令运行 **index.js** 文件:

```
node app1.js
```

**输出:**

```
GeeksforGeeks (Outside)

  GeeksforGeeks (1)
  GeeksforGeeks (2)
```

**例 2:**

**文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// console.groupCollapsed() method

// This code example demonstrate the method
// with parameter and nested groups

// Accessing console module
const console = require('console');

console.log("GeeksforGeeks ");

console.log("=========================");
console.log();

// Creating collapsed group
console.groupCollapsed("GeeksforGeeks (main Collapsed group)");
console.log();

// Printing First line of collapsed group
console.log("GeeksforGeeks (Outside)");
console.log();

// Creating First nested collapsed group
console.groupCollapsed("GeeksforGeeks (1st Nested group)");
console.log("GeeksforGeeks (1st line)");
console.log("Computer Science Portal (2nd line)");

// Ending the 1st nested group
console.groupEnd();

console.log();
console.log();

// Creating second nested collapsed group
console.groupCollapsed("GeeksforGeeks (2nd Nested group)");
console.log("Data Structure (1st line)");
console.log("Algorithms & segment tree (2nd line)");

// Ending the 2nd nested group
console.groupEnd();

console.log();

// Printing last line of Main group
console.log("Main group finished");
console.log();

// Calling groupEnd() method (It is used
// to end the group for more understanding
// the group method)
console.groupEnd();

// print from outside the Main group
console.log("GeeksforGeeks (Outside Last)");

console.log();
console.log("=========================");
```

**输出:**

```
GeeksforGeeks 
=========================

GeeksforGeeks (main Collapsed group)

  GeeksforGeeks (Outside)

  GeeksforGeeks (1st Nested group)  
    GeeksforGeeks (1st line)
    Computer Science Portal (2nd line)  

  GeeksforGeeks (2nd Nested group)      
    Data Structure (1st line)
    Algorithms & segment tree (2nd line)

  Main group finished

GeeksforGeeks (Outside Last)

=========================
```

**参考:**T2【https://nodejs . org/API/console . html # console _ console _ group collapsedT4】