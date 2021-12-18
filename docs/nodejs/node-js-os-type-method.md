# Node.js os.type()方法

> 原文:[https://www.geeksforgeeks.org/node-js-os-type-method/](https://www.geeksforgeeks.org/node-js-os-type-method/)

**os.type()方法**是 os 模块的内置应用编程接口，用于获取操作系统名称。
**语法:**

```
os.type()
```

**参数:**此方法不接受任何参数。
**返回值:**这个方法返回一个代表操作系统名称的字符串。返回值可以是 MacOS 的“达尔文”、Linux 的“Linux”和 Windows 的“Windows_NT”之一。
以下示例说明了 **os.type()方法**在 Node.js 中的使用:

**例 1:**

## java 描述语言

```
// Node.js program to demonstrate the    
// os.type() method 

// Allocating os module
const os = require('os');

// Printing os.type() value
console.log(os.type());
```

**输出:**

```
Windows_NT
```

**例 2:**

## java 描述语言

```
// Node.js program to demonstrate the    
// os.type() method 

// Allocating os module
const os = require('os');

// Printing os.type() value
var type = os.type();
switch(type) {
    case 'Darwin':
        console.log("MacOS");
        break;
    case 'Linux': 
        console.log("Linux operating system");
        break;
    case 'Windows_NT':
        console.log("windows operating system");
        break;    
    default: 
        console.log("other operating system");
}
```