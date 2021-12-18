# Node.js URL.origin API

> 原文:[https://www.geeksforgeeks.org/node-js-url-origin-api/](https://www.geeksforgeeks.org/node-js-url-origin-api/)

**url.origin** 是 **url 模块**内 **URL 类**的内置应用编程接口(API)。
**url.origin** API 用于获取 url 来源的只读序列化。

```js
Syntax: url.origin
url : It is an object created by URL constructor.
```

**例 1:**

## java 描述语言

```js
//Importing the url module
const url = require('url');

//Creating an URL_1 object with URL constructor.
const URL_1 = new URL("https://www.geeksforgeeks.org/geeks");

//Getting origin of above created URL_1 object
console.log(URL_1.origin);
```

**输出:**

![](img/507a219eeeb8ea79f85587aeedc7b7fb.png)

**注意:我们不能使用 url.origin API 设置 URL 的来源。如果我们试图这样做，那么它将被忽略，起源将不会受到影响。**
**例 2:**

## java 描述语言

```js
//Importing the url module
const url = require('url');

//Creating an URL_1 object with URL constructor.
const URL_1 = new URL("https://www.geeksforgeeks.org/geeks");

//Getting origin of above created URL_1 object
console.log(URL_1.origin);

//Setting URL_1 origin to https://www.geeks.com
URL_1.origin = "https://www.geeks.com";

//Getting origin after setting URL_1 origin
console.log(URL_1.origin);
```

**输出:**

![](img/507a219eeeb8ea79f85587aeedc7b7fb.png)