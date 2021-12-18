# node . js URL . format(URL object)API

> 原文:[https://www . geesforgeks . org/node-js-URL-format urlobject-API/](https://www.geeksforgeeks.org/node-js-url-formaturlobject-api/)

**URL.format(urlObject)** 是 URL 类提供的内置 API，它接受一个对象或字符串，并返回从该对象或字符串派生的格式化字符串。

**语法:**

```
const url.format(urlObject)

```

如果 urlObject 不是一个对象或字符串，那么它将抛出一个**类型错误**。
**返回值:**返回从 urlObject 派生的字符串。

urlObject 可以有以下字段或键:

*   草案
*   鞭打
*   作家（author 的简写）
*   主机名
*   宿主

*   港口
*   路径名
*   搜索
*   询问
*   混杂

格式化过程如下:

**result**

2.**urlObject . protocol:string**

*   如果**是一个字符串，它将被附加到结果中，如果不是未定义的，也不是字符串，那么将抛出错误。**
*   如果 **urlObject.protocol** 不以 ASCII 冒号( : )结尾，则结果后会附加文字 **':'** 。

**urlObject.slashes: boolean**

*   如果下列任一属性为真，则文字 **'//'** 被追加到结果中:
    *   **urlObject.slashaes** 为真。
    *   **urlObject.protocol** 为 **http、https、ftp、gopher 或 file** ，则即使斜线为假，斜线也会自动为真。

**urlObject.auth: string**

*   如果 **urlObject.auth** 不是未定义的，并且 urlObject.host 或 urlObject.hostname 也不是未定义的，则 auth 被附加到带有文字**“@”**的结果，而不管文字**“@”**是否出现在末尾。

**urlObject.host: string**

*   如果**是一个字符串，它会被附加到结果中，否则如果不是未定义的字符串，就会抛出错误。**
*   如果未定义，则考虑 urlObject.hostname。

**urlObject.hostname: string**

*   如果 urlObject.hostname 是一个字符串，它将被追加到结果中，否则如果不是未定义的字符串，将引发错误。
*   如果主机和主机名都已定义，则将考虑给定的主机。

**urlObject.port: (number | string)**

*   如果考虑主机名并且定义了 **urlObject.port** ，则文字“:”将与 urlObject.port 一起附加到结果中。

**urlObject.pathname: string**

*   如果 **urlObject.pathname** 是一个字符串，但不是空字符串，并且不是以文字“/”开头，则文字“/”会追加到结果中。
*   urlObject.pathname 被追加到结果中。
*   否则将抛出错误。

**urlObject.search: string**

*   如果 **urlObject.search** 是一个字符串，但不是空字符串，并且不是以文字**“？”**，则直译为**“？”**附在结果之后。
*   **urlObject.search** 被追加到结果中。
*   如果**不是字符串，则抛出错误。**

**urlObject.query: Object**

*   如果**是一个对象，那么字面上**“？”**与调用传递 **urlObject.query** 值的 **querystring** 模块的 **stringify()** 方法的输出一起附加到结果中。**
*   如果同时定义了 **urlObject.search** 和 **urlObject.query** ，则只考虑 **urlObject.search** 。

**urlObject.hash: string**

*   如果 **urlObject.hash** 是一个字符串，但不是空字符串，并且不是以文字**“#”**开头，那么文字**“#”**将被追加到结果中。
*   **urlObject.hash** 被追加到结果中。
*   否则 **urlObject.hash** 不是字符串并且不是未定义的，那么抛出错误。

**result**

**例 1**

```
/*
  node program to demonstrate the URL.format API.
*/  

//importing the module 'url'
const url = require('url');

//creating and initializing urlObject
var urlObject={
        protocol: 'https',
        hostname: 'example.com',
        port: 1800,
        pathname: 'sample/path',
        query: {
                page: 1,
                format: 'json'
        },
        hash: 'first'
    }

//getting the derieved URL from urlObject using the url.format function
var sampleUrl=url.format(urlObject);

//Display the returned value
console.log(sampleUrl.toString());

```

```
Output: https://example.com:1800/sample/path?page=1&format=json#first
```

**例 2**

```
/*
  node program to demonstrate the URL.format API.
*/  

//importing the module 'url'
const url = require('url');

//creating and initializing urlObject
var urlObject={
        protocol: 'prct',
        slashes: false,
        host: 'example.com',
        auth: 'abc',
        pathname: '/sample/path',
        search: 'something',
        hash: 'first'
    }

//getting the derieved URL from urlObject using the url.format function
var sampleUrl=url.format(urlObject);

//Display the returned value
console.log(sampleUrl.toString());
```

```
Output: prct:abc@example.com/sample/path?something#first
```

**注意:**上述程序将使用**节点 fileName.js** 命令编译运行。

**参考:**
[https://nodejs . org/API/URL . html # URL _ URL _ format _ urlobject](https://nodejs.org/api/url.html#url_url_format_urlobject)