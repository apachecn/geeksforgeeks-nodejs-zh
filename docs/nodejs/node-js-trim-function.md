# Node.js trim()功能

> 原文:[https://www.geeksforgeeks.org/node-js-trim-function/](https://www.geeksforgeeks.org/node-js-trim-function/)

**trim()函数**是 [Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 的字符串函数，用于删除字符串中的空格。

**语法:**

```
*string*.trim()
```

**参数:**该函数不接受任何参数。

**返回值:**函数返回不带空格的字符串。

以下程序演示了 trim()功能的工作原理:

**节目 1:**

```
function trim(str) {

    // Use trim() function
    var trimContent = str.trim();

    console.log(trimContent);
}

// Initialize variable
var str = "       *GeeksforGeeks*          ";

// Function call
trim(str);
```

**输出:**

```
*GeeksforGeeks*
```

**节目 2:**

```
function trim(str) {

    // Use trim() function
    var trimContent = str.trim();

    console.log(trimContent);
}

// Initialize variable
var str = "       Welcome to GeeksforGeeks          ";

// Function call
trim(str);    
```

**输出:**

```
Welcome to GeeksforGeeks
```