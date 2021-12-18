# node . js URL . domain toascii

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-URL-domain toascii/

**url.host** 是一个内置于 url 模块中的类 URL 的应用编程接口。

它返回域的 [Punycode](https://tools.ietf.org/html/rfc5891#section-4.4) ASCII 序列化。如果域是无效域，则返回空字符串。

**语法:**

```js
const url.domainToASCII
```

**域值:**字符串

**返回值:**字符串

**例:**

```js
const url = require('url');

console.log(url.domainToASCII('español.com'));

console.log(url.domainToASCII('??.com'));

console.log(url.domainToASCII('xn--iñvalid.com'));
```

**输出:**

```js
xn--espaol-zwa.com
xn--fiq228c.com
// Prints an empty string in the 3'rd case

```

**注意:**它执行 url.domainToUnicode()的逆运算。