# Node.js indexOf()函数

> 原文:[https://www.geeksforgeeks.org/node-js-indexof-function/](https://www.geeksforgeeks.org/node-js-indexof-function/)

函数的**索引是一个来自 [Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 的字符串函数，用于查找一个带有另一个字符串的字符串。**

**语法:**

```
*str1*.indexOf( *str2* )
```

**参数:**该函数使用两个参数，如上所述，如下所述:

*   **str1:** It holds the string content of another string to be searched.
*   **str2:** It holds the search string.

**返回值:**函数返回传递参数的索引。

以下程序演示了 indexOf()函数的工作原理:

**节目 1:**

```
function findIndex(str) {
    var index = str.indexOf("awesome");
    console.log(index);
}

var str = "gfg is awesome";

findIndex(str);
```

**输出:**

```
7
```

**节目 2:**

```
function findIndex(str1, str2) {

    var index = str1.indexOf(str2);

    console.log(index);
}

var str1 = "Welcome to GeeksforGeeks";
var str2 = "to"

findIndex(str1, str2);
```

输出:

```
8
```