# Node.js URL.resolve(from，to) API

> 原文:[https://www . geesforgeks . org/node-js-URL-resolvefromto-API/](https://www.geeksforgeeks.org/node-js-url-resolvefromto-api/)

URL . resolve(from，to) 是类 **URL** 的内置方法，它相对于**基本 URL** 解析**目标 URL** 。

### 语法:

```
url.resolve(from, to);

```

*   **从:** ( *类型:字符串*)解析的基本网址。
*   **到:** ( *类型:字符串*)正在解析的“href”网址。

### 返回值:

它通过在**中给定的参数从**的**网址返回到**网址(类型:字符串)。

### 解析目标网址:

**1。**以正斜杠(“/”)开头–它将替换基本网址域后的整个路径。
T3】2。前面没有正斜杠(“/”)–它将替换基本网址路径中正斜杠(“/”)后的最后一个单词。

### 示例:

```
// node program to demonstrate the  
// url.resolve(from, to) method  

//importing the module 'url' 
const url = require('url'); 

//We can directly console.log() return value of the method

//Method 1:
console.log(url.resolve("http://www.google.com/", "/one"));                  
console.log(url.resolve("http://www.google.com/one/two/three", "/four"));    

//Method 2:
console.log(url.resolve("http://www.google.com/", "one"));                  
console.log(url.resolve("http://www.google.com/one/two/three", "four"));    
```

```
OUTPUT: 
http://www.google.com/one
http://www.google.com/four

http://www.google.com/one
http://www.google.com/one/two/four

```

### 注意:

这段代码可以在命令提示符下用 node 命令运行。(例如*节点文件名*)

### 参考文献:

[https://nodejs.org/api/url.html#url_url_resolve_from_to](https://nodejs.org/api/url.html#url_url_resolve_from_to)