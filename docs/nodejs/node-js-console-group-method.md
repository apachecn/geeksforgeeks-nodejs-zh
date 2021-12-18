# Node.js console.group()方法

> 原文:[https://www.geeksforgeeks.org/node-js-console-group-method/](https://www.geeksforgeeks.org/node-js-console-group-method/)

**控制台。** **组()** **方法**是控制台模块内置的应用编程接口，用于分组打印传递的内容。它指示消息组的开始。要结束这个组，我们可以使用**控制台。groupEnd()** 方法。

**语法:**

```
console.group([label]);
```

**参数:**此方法只接受一个参数，如上所述，如下所述:

1.  **Label:** Label of the group you grouped on the console. This parameter is not required, it is optional and can be run on the console. Group () method without passing the label parameter.

**参数值:**

1.  **type:** string
2.  **Required:** Optional

**返回值:**这个方法不返回任何东西，而是将控制台上的内容用标签分组(如果提供的话),否则就不用标签。

以下示例说明了**控制台的使用。Node.js 中的 group()** 方法。

**例 1:**

## index . js

```
// Node.js program to demonstrate the 
// console.group() method 
// This code example demonstrate the
// method without parameter

// Accessing console module 
const console = require('console'); 

console.log("GeeksforGeeks");
console.log();

// Creating  First Group
console.group();

// Printing First Statement of Group 
console.log("1st print from the first group");

// Printing Second Statement of Group 
console.log("2nd print from the first group");

// Ending  the group 
console.groupEnd();
console.log();
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**控制台输出:**

```
GeeksforGeeks

 1st print from the first group
 2nd print from the first group

```

**例 2:**

## index . js

```
// Node.js program to demonstrate the 
// console.group() method 

// This code example demonstrate the method
// with parameter and nested groups

// Accessing console module 
const console = require('console');

console.log("GeeksforGeeks ");

console.log("==========================");
console.log();

// Creating First group
console.group("This is the starting main group");
console.log();

// Printing First statement of Group 
console.log("1st group and not from any nested group");
console.log();

// Creating nested group in First group 
console.group("Starting of the 1st Nested group");

// Printing 1st line of nested group
console.log("Hello Geeks for Geeks from "
    + "1st Main Nested group");

// Printing 2nd line of nested group 
console.log("Computer Science Portal(GeeksforGeeks)"
    + " from 1st Main Nested group");

// Ending of the first nested group
console.groupEnd();

console.log();
console.log();

// Creating second nested group 
console.group("Starting of the 2nd Main Nested group");

// Printing 1st line of second nested group
console.log("Hello from 2nd Main Nested group");

// Printing 2nd line of second nested group
console.log("Hello from 2nd Main Nested group");

// Ending of the second nested group
console.groupEnd();
console.log();

// Printing last line of the group
console.log("Now Main group will end");

console.log();

// Calling groupEnd() method (It is used to 
// end the group for more understanding 
// the group method) 
console.groupEnd();

// Printing from outside the Main group
console.log("This the Hello from GeeksforGeeks"
    + " from outside the Main Group");

console.log();
console.log("===========================");
```

**控制台输出:**

```
GeeksforGeeks 
==========================

This is the starting main group

  1st group and not from any nested group

  Starting of the 1st Nested group
    Hello Geeks for Geeks from 1st Main Nested group
    Computer Science Portal(GeeksforGeeks) 
      from 1st Main Nested group

  Starting of the 2nd Main Nested group
    Hello from 2nd Main Nested group
    Hello from 2nd Main Nested group

  Now Main group will end

This the Hello from GeeksforGeeks from 
  outside the Main Group        

===========================

```

**参考:**[https://nodejs . org/API/console . html # console _ console _ group _ label](https://nodejs.org/api/console.html#console_console_group_label)