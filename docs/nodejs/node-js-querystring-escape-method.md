# Node.js querystring.escape()方法

> 原文:[https://www . geesforgeks . org/node-js-query string-escape-method/](https://www.geeksforgeeks.org/node-js-querystring-escape-method/)

**querystring.escape()函数**用于从普通字符串生成百分比编码的查询字符串。这个方法非常类似于浏览器的 **encodeURIComponent** 功能。此方法对给定的字符串执行百分比编码，这意味着它通过使用 **%** 符号将任何字符串编码为网址查询字符串。此方法遍历字符串，并将%编码放在需要的地方。querystring.stringify()方法在内部使用此方法，通常不直接使用。

**语法:**

```
querystring.escape(str);
```

**参数:**该函数只接受一个参数，如下所述。

*   **str:** is a string to be encoded into a query string.

**返回值:**返回一个包含给定字符串产生的查询的字符串。

下面是解释查询 string.escape 函数概念的例子。

**示例 1:** 在本例中，我们对一个简单的字符串进行编码。

## 

```
//Importing querystring module
const querystring = require("querystring")

// String to be encoded
let str = "I love geeksforgeeks";

// Using the escape function to the string
let encodedURL = querystring.escape(str);

// Printing the encoded url
console.log(encodedURL)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
encoded url : I%20love%20geeksforgeeks
```

**示例 2:** 在本例中，我们使用 **querystring.escape( )** 函数和 **encodeURIComponent** 函数对字符串进行编码，并打印这两个函数的输出。

## index . js

```
//Importing querystring module
const querystring = require("querystring")

// String to be encoded
let str = "I love geeksforgeeks";

// Using the escape function to the string
let encodedURL1 = querystring.escape(str);

// Using the encodedURIComponent function
let encodedURL2 = encodeURIComponent(str);

// Printing the encoded urls
console.log("encoded url using escape: " + encodedURL1)
console.log("encoded url using encodeURIComponent: " + encodedURL2)

// Printing if the both encodings are equal
if(encodedURL1 === encodedURL2){
    console.log("Both are the same results.")
}
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
encoded url using escape: I%20love%20geeksforgeeks
encoded url using encodeURIComponent: I%20love%20geeksforgeeks
Both are the same results.
```

**参考:**[https://nodejs . org/API/query string . html # query string _ query string _ escape _ str](https://nodejs.org/api/querystring.html#querystring_querystring_escape_str)