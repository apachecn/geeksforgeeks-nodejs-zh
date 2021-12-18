# Node.js substr()函数

> 原文:[https://www.geeksforgeeks.org/node-js-substr-function/](https://www.geeksforgeeks.org/node-js-substr-function/)

**substr()函数**是 [Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 的字符串函数，用于从给定的字符串中提取子字符串。

**语法:**

```js
*string*.substr(*index*, *length*)

```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **Index:** This parameter holds the starting index of the specified substring.
*   **Length:** This parameter stores the length of substring.

**返回值:**函数返回给定字符串的子字符串。

下面的程序演示了 substr()函数的工作原理:

**节目 1:**

```js
function findsubstr(str) {

    var substring = str.substr(11, 13);

    console.log(substring);
}

var str = "Welcome to GeeksforGeeks";

findsubstr(str);
```

**输出:**

```js
GeeksforGeeks
```

**节目 2:**

```js
function findsubstr(str, index, length) {

    var substring = str.substr(index, length);

    console.log(substring);
}

var str = "Welcome to GeeksforGeeks";

var index = 11, length = 13;

findsubstr(str, index, length);
```

**输出:**

```js
GeeksforGeeks
```