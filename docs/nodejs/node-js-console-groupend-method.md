# Node.js console.groupEnd()方法

> 原文:[https://www . geesforgeks . org/node-js-console-group end-method/](https://www.geeksforgeeks.org/node-js-console-groupend-method/)

**控制台。groupEnd()** **方法**是控制台模块的内置应用编程接口，用于通过调用方法 console.group()或 console.groupCollapsed()结束已启动的组。它指示消息组的结束。

**语法:**

```
console.groupEnd();
```

**参数:**此方法不接受任何参数。

**返回值:**这个方法不返回任何东西，只是结束控制台上的组。

以下示例说明了**控制台的使用。Node.js 中的 groupEnd()** 方法

**例 1:**

## index . js

```
// Node.js program to demonstrate the 
// console.groupEnd() method 

// This code example demonstrate the method
// with console.groupCollapsed() method

// Accessing console module 
const console = require('console');

console.log("GeeksforGeeks");
console.log();

console.groupCollapsed();

// Printing First line of Group 
console.log("1st print from the first Collapsed group");

// Printing Second line  of Group
console.log("2nd print from the first Collapsed group");

// Calling the groupEnd() method
console.groupEnd();
console.log();

// Printing out of the group
console.log("GeeksforGeeks after the Ending of the group");
console.log();
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**控制台输出:**

```
GeeksforGeeks

  1st print from the first Collapsed group
  2nd print from the first Collapsed group

GeeksforGeeks after the Ending of the group
```

**例 2:**

## index . js

```
// Node.js program to demonstrate the 
// console.group() method 

// This code example demonstrate the
// method with console.group() method

// Accessing console module 
const console = require('console');

console.log("GeeksforGeeks ");
console.log("================================");
console.log();

// Creating main group
console.group("This is the starting main group");
console.log();

// Printing First line of group 
console.log("1st group and not from any nested group");
console.log();

// Creating first nested group inside main group
console.group("Starting of the 1st Nested group");

// Printing 1st line 
console.log("Hello Geeks for Geeks from "
    + "1st Main Nested group");

// Printing 2nd line 
console.log("Computer Science Portal(Geeks for "
    + "Geeks) from 1st Main Nested group");

// Ending of the first nested group
// Calling the groupEnd() method
console.groupEnd();

console.log();
console.log();

// Creating second nested group 
console.group("Starting of the 2nd Main Nested group");

// Printing 1st line
console.log("Hello from 2nd Main Nested group");

// Printing 2nd line 
console.log("Hello from 2nd Main Nested group");

// Ending of the first nested group
// calling the groupEnd() method
console.groupEnd();

console.log();

// Printing last line of the group
console.log("Now Main group will end");

console.log();

// Calling groupEnd() method (It is used to 
// end the group for more understanding
// the group method) 
// Calling the groupEnd() method
console.groupEnd();

// Printing from outside the Main group
console.log("This the Hello from GeeksforGeeks"
    + " from outside the Main Group");

console.log();
console.log("===================================");
```

**控制台输出:**

```
GeeksforGeeks 
================================

This is the starting main group

  1st group and not from any nested group

  Starting of the 1st Nested group
    Hello Geeks for Geeks from 1st Main Nested group
    Computer Science Portal(Geeks for Geeks) 
    from 1st Main Nested group

  Starting of the 2nd Main Nested group
    Hello from 2nd Main Nested group
    Hello from 2nd Main Nested group

  Now Main group will end

This the Hello from GeeksforGeeks from outside the Main Group

===================================

```

**参考:**[https://nodejs . org/API/console . html # console _ console _ group end](https://nodejs.org/api/console.html#console_console_groupend)