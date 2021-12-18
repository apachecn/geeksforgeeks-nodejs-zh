# node . js urlobject . pathname API

> 原文:[https://www . geesforgeks . org/node-js-URL object-pathname-API/](https://www.geeksforgeeks.org/node-js-urlobject-pathname-api/)

借助 urlObject.pathname()方法，我们可以找到给定主机名所使用的路径的名称。这包含从主机(带端口)开始，在查询或哈希组件开始之前的所有内容，由 ASCII 问号(？)或哈希(#)字符。

```js
Syntax: urlObject.pathname()
Return: Returns the pathname used(i.e.'/p/a/t/h')
```

例 1:

```js
const url = require('url'); 

var address =  
'https://u:p@www.example.com:777/a/b?c=d&e=f#g'; 

// Parse the address: 
var q = url.parse(address, true); 

/* The parse method returns an object containing 
 URL properties */

console.log(q.pathname); 
```

输出:

```js
/a/b
```

例 2:

```js
const url = require('url'); 

var address =  
'http://example.com/'; 

// Parse the address: 
var q = url.parse(address, true); 

/* The parse method returns an object containing 
 URL properties */

console.log(q.pathname); 
```

输出:

```js
/
```

**支持的浏览器:**

*   谷歌铬
*   工业管理学(Industrial Engineering)
*   边缘
*   歌剧
*   苹果 Safari