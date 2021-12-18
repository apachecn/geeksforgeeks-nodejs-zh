# node . js URL . hash API

> 原文:[https://www.geeksforgeeks.org/node-js-url-hash-api/](https://www.geeksforgeeks.org/node-js-url-hash-api/)

**url.hash** 是 **url** 模块中 **url** 类的内置应用编程接口，用于获取和设置 URL 的片段部分。

**语法:**

```js
url.hash
```

**返回值:**获取并设置 URL 的片段部分。

下面的程序说明了**方法的使用:**

**例 1:**

## java 描述语言

```js
// node program to demonstrate the 
// url.hash API as Setter 

// creating and initializing myURL
const myURL = new URL('https://example.org/foo#ram');

// Display href value of myURL before change
console.log("Before Change");
console.log(myURL.href);

// assigning fragment portion
// using hash 
console.log();
myURL.hash = 'rahim';

// Display href value of myURL after change
console.log("After Change");
console.log(myURL.href);
```

**输出**:

```js
Before Change
https://example.org/foo#ram

After Change
https://example.org/foo#rahim
```

**例 2:**

## java 描述语言

```js
// node program to demonstrate the 
// url.hash API as Getter 

// creating and initializing myURL
const myURL = new URL('https://example.org/foo#ram');

// getting the fragment portion
// using hash 
const hash = myURL.hash;

// Display hash value 
console.log(hash);
```

**输出:**

```js
#ram
```

**注意**:上述程序可以使用**节点 myapp.js** 命令运行。

**参考:**
[https://nodejs . org/dist/latest-v10 . x/docs/API/URL . html # URL _ hash](https://nodejs.org/dist/latest-v10.x/docs/api/url.html#url_url_hash)