# Node.js URL.username API

> 原文:[https://www.geeksforgeeks.org/node-js-url-username-api/](https://www.geeksforgeeks.org/node-js-url-username-api/)

**URL.username** 是**节点内 **URL 类**的内置应用编程接口(API)。JS** 。
**URL.username** API 用于获取和设置 URL 的用户名。

```js
Syntax: url.username
url : It is an object created by URL constructor.
```

**示例 1:(获取 URL 的用户名)**

## java 描述语言

```js
//Creating an URL_1 object with URL constructor.
const URL_1 = new URL("https://ashish:ashish123@www.geeksforgeeks.org");

//Getting username of above created URL_1 object
console.log(URL_1.username);
```

**输出:**

![](img/570cf7ce2187639f70de01d2c74d8aa7.png)

**例 2:(设置网址用户名)**

## java 描述语言

```js
//Creating an URL_1 object with URL constructor.
const URL_1 = new URL("https://ashish:ashish123@www.geeksforgeeks.org/geeks");

//Getting username of above created URL_1 object
console.log("Before changing username URL is:")
console.log(URL_1.href);
console.log("username: "+ URL_1.username);

//Setting URL_1 username to ashu
URL_1.username = "ashu";

//Getting username after setting it to ashu
console.log("After changing username URL is:")
console.log(URL_1.href);
console.log("username: "+ URL_1.username);
```

**输出:**

![](img/92d831457471395a8cb9ba92fb5edb97.png)