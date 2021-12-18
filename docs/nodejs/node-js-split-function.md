# Node.js split()功能

> 原文:[https://www.geeksforgeeks.org/node-js-split-function/](https://www.geeksforgeeks.org/node-js-split-function/)

**split()函数**是 [Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 的一个字符串函数，用于将字符串拆分为子字符串。该函数以数组形式返回输出。
**语法:**

```
*string*.split( *separator* )
```

**参数:**该函数接受单参数**分隔符**，该分隔符保存要分割字符串的字符。
**返回值:**函数返回拆分后的字符串，并生成数组作为结果。
以下程序演示 split()功能的工作:
**程序 1:**

## java 描述语言

```
function splitStr(str) {

    // Function to split string
    var string = str.split("*");

    console.log(string);
}

// Initialize string
var str = "Welcome*to*GeeksforGeeks";

// Function call
splitStr(str);    
```

**输出:**

```
[ 'Welcome', 'to', 'GeeksforGeeks' ]
```

**节目 2:**

## java 描述语言

```
function splitStr(str, separator) {

    // Function to split string
    var string = str.split(separator);

    console.log(string);
}

// Initialize string
var str = "GeeksforGeeks/A/computer/science/portal";

var separator = "/";

// Function call
splitStr(str, separator);
```

**输出:**

```
[ 'GeeksforGeeks', 'A', 'computer', 'science', 'portal' ]
```