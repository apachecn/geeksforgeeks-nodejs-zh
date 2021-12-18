# Node.js 切片()功能

> 原文:[https://www.geeksforgeeks.org/node-js-slice-function/](https://www.geeksforgeeks.org/node-js-slice-function/)

**切片()函数**是 [Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 的字符串函数，用于从字符串中提取子字符串。

**语法:**

```

*string*.slice( *start*, *end* )

```

**参数:**这个函数使用上面提到的和下面描述的三个参数:

*   **String:** It holds the contents of the string. A substring is extracted from the string.
*   **Start:** This parameter holds the starting index of substring.
*   **End:** This parameter stores the ending index od of substring.

**返回类型:**函数返回子串。

下面的程序演示了该函数的工作原理:

**节目 1:**

```
function findsubstr(str) {

    var index = str.slice(12, 25);

    console.log(index);
}

var str = "Welcome to GeeksforGeeks";

findsubstr(str);
```

**输出:**

```
GeeksforGeeks
```

**节目 2:**

```
function findsubstr(str, start, end) {

    var index = str.slice(start, end);

    console.log(index);
}

var str = "Welcome to GeeksforGeeks";

var start = 0;
var end = 6;

findsubstr(str, start, end);
```

**输出:**

```
Welcome
```