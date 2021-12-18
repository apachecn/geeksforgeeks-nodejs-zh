# Node.js urlObject.hash API

> 原文:[https://www.geeksforgeeks.org/node-js-urlobject-hash-api/](https://www.geeksforgeeks.org/node-js-urlobject-hash-api/)

在我们继续学习关于网址对象应用编程接口之前，我们需要了解一个关于网址的简介。

如果你想提供实用程序来解析或解析你的网址，我们可以通过网址模块来实现。

我们可以把网址模块分成两部分:-这是-网址字符串和网址对象。网址对象散列是网址对象的一部分，它通常基于传统的应用编程接口(尽管一个更新的应用编程接口也由 WHATWG 网址标准的名称提供)

**urlObject.hash:** 用于标识 URL 的“片段”部分。该属性还包括#字符。

```js
For example: '#hash'.
```

**语法**

```js
urlObject.hash
```

**例:**

```js
const url = require('url');
const reqUrl = 'www.example.com/hi#file?=newFile'
const urlObject = url.parse(reqUrl, true);

console.log(urlObject.hash);
```

**输出:**

```js
#file?=newFile
```