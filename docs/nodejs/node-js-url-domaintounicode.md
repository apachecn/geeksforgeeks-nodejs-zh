# node . js URL . domaintounicode

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-URL-domain tounicode/

**url . domain unicode**是一个内置的应用程序编程接口，具有 URL 模块中的类 URL。

它返回域的 Unicode 序列化。如果域无效，则返回空字符串。

**语法:**

```
const url.domainToASCII
```

**域值:**字符串

**返回值:**字符串

**例:**

```
const url = require('url');
console.log(url.domainToUnicode('xn--espaol-zwa.com'));

console.log(url.domainToUnicode('xn--fiq228c.com'));

console.log(url.domainToUnicode('xn--iñvalid.com'));
```

**输出:**

```
español.com
??.com
//Empty String will be printed for third case

```

**注意:**它对 url.domainToASCII()执行反向操作。