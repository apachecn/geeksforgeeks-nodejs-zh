# Node.js urlObject.host API

> 原文:[https://www.geeksforgeeks.org/node-js-urlobject-host-api/](https://www.geeksforgeeks.org/node-js-urlobject-host-api/)

网址解析和解析工具由网址模块提供。
URL 字符串是包含各种多重有意义成分的结构化字符串。解析时，将返回一个 URL 对象，其中包含这些组件的属性。

**url.host()** 将 url 中的主机名作为**字符串返回。**
**例:**

```js
*http://localhost:8080/register
localhost:8080 - is the host name.*

```

```js
**https://geeksforgeeks.org/practice
geeksforgeeks.org - is the host name.**
```

*在下面的例子中，我们首先创建一个网址对象。然后在使用。host()函数，我们将获取 URL 中的主机名作为输出。*

```js
*//Importing the url module
const url=require('url');

//creating a new url object
var link = new URL("https://google.com/coding_challenges");

//Using the .host() function to print the host name in the url
console.log(link.host);*
```

```js
***OUTPUT:**
google.com*
```