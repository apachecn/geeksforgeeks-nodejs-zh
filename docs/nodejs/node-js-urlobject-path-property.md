# Node.js urlObject.path 属性

> 原文:[https://www . geesforgeks . org/node-js-URL object-path-property/](https://www.geeksforgeeks.org/node-js-urlobject-path-property/)

在本文中，我们将学习关于 urlObject.path API 的知识。 *urlObject.path API* 属性是路径名和搜索组件的串联。Pathname 指的是 URL 中的文件路径，搜索组件指的是具有固定限制的查询和哈希字符串，例如问号(？)或哈希(#)字符。不执行路径解码。

让我们考虑一个'http://user:pass@sub.example.com:8080/p/a/t/h?的网址查询=字符串#hash '

```
Syntax: urlObject.path
Return: '/p/a/t/h?query=string'
```

*urlObject.path 返回'/p/a/t/h？由 url.parse()函数返回后的“query=string”。*

**例 1: Index.js**

## java 描述语言

```
//Importing url module
const http = require('url'); 

// Creating a demo URL 
const myURL = 
'http://user:pass@sub.example.com:8080/p/a/t/h?query=string#hash'; 

// Parsing the Address
var q = http.parse(myURL, true);    

// Displaying the path  
console.log(q.path);    
```

**执行命令:**

```
node index.js
```

**控制台输出:**

```
/p/a/t/h?query=string
```

**例 2:(改变路径)**

## java 描述语言

```
//Importing the url module
const http = require('url'); 

// Creating a demo URL 
const myURL = 
'http://user:pass@sub.example.com:8080/p/a/t/h?query=string#hash'; 

var q = http.parse(myURL, true);    

// Display path value of myURL before change 
console.log("Before Change");  
console.log(q.path);    
console.log(); 

// Changing the path
q.path='/s/k/t/j?query=abc@gmail.com' 

// Printing the changed path
console.log("After Change"); 
console.log(q.path);
```

**执行命令:**

```
node index.js
```

**控制台输出:**

```
Before Change
/p/a/t/h?query=string

After Change
/s/k/t/j?query=abc@gmail.com
```