# Node.js querystring.unescape()方法

> 原文:[https://www . geesforgeks . org/node-js-query string-une scape-method/](https://www.geeksforgeeks.org/node-js-querystring-unescape-method/)

在指定的字符串上，querystring.unescape()方法解码 URL 百分比编码的字符。此方法将百分比编码字符串转换为普通字符串。这意味着它通过删除%符号将任何百分比编码字符串解码为正常字符串。此方法遍历字符串，并在指定字符串上需要的地方移除%编码。

queryString.unescape()函数由 querystring.parse()使用，不太适合直接使用。它的导入主要是为了使程序代码能够有一个可变的解码实现，如果需要的话，可以将 queryString.unescape 分配给一个不同的函数。

**语法:**

```
querystring.unescape(str);
```

**参数:**该函数只接受一个参数，如下所述。

*   **字符串:**是将被解码为正常字符串的 URL 百分比编码字符。

**返回值:**解码网址百分比编码字符后返回正常字符串。

**注意:**使用以下命令安装 querystring。

```
npm i querystring
```

下面是解释查询 string.unescape 函数概念的例子。

**示例 1:** 在本例中，我们对 URL 百分比编码的字符串进行编码。

**Index.js**

## java 描述语言

```
//Importing querystring module
import querystring from "querystring" 

// String to be decoded
let str = "I%20love%20geeksforgeeks";

// Using the unescape function to decode
let decodedURL = querystring.unescape(str);

// Printing the decoded url
console.log(decodedURL)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Decoded string: I love geeksforgeeks
```

**示例 2:** 在本例中，我们使用 **querystring.unescape( )** 函数和 **decodeURIComponent** 函数对 URL 百分比编码的字符串进行解码，并打印这两个函数的输出。

## java 描述语言

```
//Importing querystring module
import querystring from "querystring" 

// String to be encoded
let str = "I%20love%20geeksforgeeks";

// Using the unescape function to the string
let decodeURL1 = querystring.unescape(str);

let decodeURL2 = decodeURIComponent(str);
// Printing the decoded url
console.log("Decoded string using unescape: " + decodeURL1)
console.log("Decoded string using decodeURIComponent: " + decodeURL2)

if(decodeURL2 === decodeURL1)
console.log("both strings are equal")
```

**输出:**

```
Decoded string using unescape: I love geeksforgeeks
Decoded string using decodeURIComponent: I love geeksforgeeks
both strings are equal
```