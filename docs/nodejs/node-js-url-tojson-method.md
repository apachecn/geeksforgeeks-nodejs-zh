# Node.js URL.toJSON()方法

> 原文:[https://www.geeksforgeeks.org/node-js-url-tojson-method/](https://www.geeksforgeeks.org/node-js-url-tojson-method/)

node.js url 模块中的 **url.toJSON()方法**用于返回 URL 对象的序列化 URL。此方法的返回值等效于 URL.href 和 url.toString()方法。如果一个网址对象是使用 JSON.stringify()方法序列化的，那么它将被自动调用。

**语法:**

```
url.toJSON()
```

**参数:**此方法不接受任何参数。

**返回值:**此方法返回 URL 对象的序列化 URL。

下面的例子说明了 Node.js 中的 url.toJSON()方法:

**例 1:**

```
// node program to demonstrate the
// url.toJSON() method in node.js

// Require an URL module
const url = require('url');

// Creating and initializing myURL variable
var urls = [
    new URL('https://www.geeksforgeeks.com'),
    new URL('https://www.google.com'),
    new URL('https://www.mygeeks.com')
];

// Display result
console.log(JSON.stringify(urls));
```

**输出:**

```
[
    "https://www.geeksforgeeks.org/",
    "https://www.google.com/",
    "https://www.mygeeks.com/"
]

```

**例 2:**

```
// node program to demonstrate the
// url.toJSON() method in node.js

// Require an URL module
const url = require('url');

// Creating and initializing myURL variable
var myurl = [
    new URL('https://www.geeksforgeeks.org'),
    new URL('https://write.geeksforgeeks.org'),
    new URL('https://www.practice.geeksforgeeks.org'),
    new URL('https://www.demo.geeksforgeeks.org'),
    new URL('https://write.geeksforgeeks.org'),
];

// Display result
console.log(JSON.stringify(myurl));
```

**输出:**

```
[
    "https://www.geeksforgeeks.org/",
    "https://write.geeksforgeeks.org/",
    "https://www.practice.geeksforgeeks.org/",
    "https://www.demo.geeksforgeeks.org/",
    "https://write.geeksforgeeks.org/"
]

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/URL . html # URL _ URL _ tojson](https://nodejs.org/api/url.html#url_url_tojson)