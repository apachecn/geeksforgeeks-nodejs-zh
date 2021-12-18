# node . js URL . domaintonunicode()方法

> 原文:[https://www . geesforgeks . org/node-js-URL-domain unicode-method/](https://www.geeksforgeeks.org/node-js-url-domaintounicode-method/)

**URL . domaintonunicode()**方法是一个内置的应用程序编程接口类 **URL** 与 **url** 模块，用于获取特定 ASCII 值的域。

**语法:**

```
const url.domainToUnicode(domain)
```

**参数:s** 该方法以 ASCII 值为参数，即将转换为 Unicode。

**返回值:**该方法返回特定域的 unicode 值。

下面的程序说明了**URL . domaintonunicode()**方法的使用。
T3】例 1:

```
// Node.js program to demonstrate the 
// URL.domainToUnicode() method

// Importing the 'url' module
const http = require('url');

// Getting Unicode value
// by using domainToUnicode() api
const ascivalue = http.domainToUnicode(
            "xn--espaol-zwa.com");

// Display result for each value entry
console.log("Unicode value : " + ascivalue);

// Getting Unicode value
// by using domainToUnicode() api
const ascivalue1 = http.domainToUnicode("google.com");

// display result for each value entry
console.log("\nUnicode value : " + ascivalue1);
```

**输出:**

```
ASCII value : xn--espaol-zwa.com

ASCII value : google.com

```

**例 2:**

```
// Node.js program to demonstrate the 
// URL.domainToUnicode() API as Setter

// Importing the module 'url'
const http = require('url');

// Getting Unicode value
// by using domainToUnicode() api
const ascivalue = http.domainToUnicode(
            "geeksforgeeks.com");

// Display result for each value entry
console.log("Unicode value : " + ascivalue);

// Getting Unicode value
// by using domainToUnicode() api
const ascivalue1 = http.domainToUnicode("xn--iñvalid.com");

// Display result for each value entry
console.log("\nUnicode value : " + ascivalue1);
```

**输出:**

```
Unicode value : geeksforgeeks.com

Unicode value :

```

**注意**:以上程序不会在在线 JavaScript 和脚本编辑器上运行。

**参考:**[https://nodejs . org/dist/latest-v 14 . x/docs/API/URL . html # URL _ URL _ domaintonunicode _ domain](https://nodejs.org/dist/latest-v14.x/docs/api/url.html#url_url_domaintounicode_domain)