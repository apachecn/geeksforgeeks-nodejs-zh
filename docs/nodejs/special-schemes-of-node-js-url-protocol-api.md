# node . js URL . protocol API 特殊方案

> 原文:[https://www . geesforgeks . org/special-schemes-of-node-js-URL-protocol-API/](https://www.geeksforgeeks.org/special-schemes-of-node-js-url-protocol-api/)

**url.protocol** 是 url 模块内内置的类 URL 的应用编程接口，用于获取和设置 URL 的协议方案。

**语法:**

```js
const url.protocol
```

**返回值:**获取并设置网址的协议方案

**示例 1:** 本示例将特殊协议更改为假设协议，如 http- > https。

## Javascript

```js
// Node program to demonstrate the  
// url.protocol API as Setter  
// Changing of protocols to special
// protocols like http->https

// Importing the module 'url' 
const http = require('url'); 

// Creating and initializing myURL 
const myURL = new URL('http://gfg.org/foo'); 

// Display href value of myURL before change 
console.log("Before Change"); 

console.log(myURL.href); 

// Assigning protocol portion 
// using protocol 
console.log(); 
myURL.protocol = 'https'; 

// Display href value of myURL after change 
console.log("After Change"); 
console.log(myURL.href); 
```