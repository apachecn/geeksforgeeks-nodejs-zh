# Node.js console.dirxml()方法

> 原文:[https://www . geesforgeks . org/node-js-console-dirxml-method/](https://www.geeksforgeeks.org/node-js-console-dirxml-method/)

**console.dirxml()方法**通过传递接收到的参数调用 [console.log()](https://www.geeksforgeeks.org/node-js-console-log-function/) 方法，这个元素不产生任何 xml 格式。

**语法:**

```
console.dirxml(object_or_element)
```

**参数:**这个函数接受以下参数:

*   **Object:** This method takes a JavaScript object or element.

**返回值:**该方法返回传递的对象或元素。

下面的例子说明了 **process.memoryUsage()** 方法在 Node.js 中的使用

**例 1:**

## index . js

```
// Importing console module
const console = require('console'); 

var a = 'GeeksforGeeks';

// Calling console.dirxml() function
console.dirxml(a)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
GeeksforGeeks
```

**示例 2:** 使用以下代码创建一个 index.js 文件。

## 

```
// Importing console module
const console = require('console'); 

// Calling console.dirxml() function
console.dirxml("Hi there, Geeks")
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Hi there, Geeks
```

**参考:**[https://nodejs . org/API/console . html # console _ console _ dirxml _ data](https://nodejs.org/api/console.html#console_console_dirxml_data)