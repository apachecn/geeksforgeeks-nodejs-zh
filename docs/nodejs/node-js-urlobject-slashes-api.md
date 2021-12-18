# node . js urlobject . slashs API

> 原文:[https://www . geesforgeks . org/node-js-URL object-slashes-API/](https://www.geeksforgeeks.org/node-js-urlobject-slashes-api/)

urlObject.slashes 属性用于检查 URL 的协议(http 或 https)中冒号(:)后是否需要 ASCII 值的正斜杠字符(/)。它返回布尔值。

**语法:**

```js
urlObject.slashes
```

**返回值:**如果需要两个 ASCII 值正斜杠，urlObject.slashes 属性返回 true，否则返回 false。

下面的程序说明了 urlObject.slashes 属性的使用:

**例 1:**

```js
// Node program to demonstrate the 
// urlObject.slashes API as Setter

// Importing the module 'url-parse'
var parse = require('url-parse'); 

// Use command 'npm install url-parse' in
// command prompt to import this module
var url = parse('www.geeksforgeeks.org');

// Display result in console
console.log(url.slashes);
```

**输出:**

```js
false
```

**例 2:**

```js
// Node program to demonstrate the  
// urlObject.slashes API as Setter

// Importing the module 'url-parse'
var parse = require('url-parse'), 
url = parse('https://example.com/geek/login');

// Disaply the result in console view
console.log(url.slashes)
```

**输出:**

```js
true
```

**注意:**以上程序将使用**节点 app.js** 命令编译运行。

**参考:**[https://nodejs . org/API/URL . html # URL _ URL object _ slashes](https://nodejs.org/api/url.html#url_urlobject_slashes)