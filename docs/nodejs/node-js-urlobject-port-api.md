# Node.js urlObject.port API

> 原文:[https://www.geeksforgeeks.org/node-js-urlobject-port-api/](https://www.geeksforgeeks.org/node-js-urlobject-port-api/)

Node 中的 **urlObject.port()** 方法用于获取主机名中主机组件的数字端口部分。
返回网址的端口号，否则**无**如果网址中没有端口号。

```

Syntax : urlObject.port()
Return : Returns the URL’s port number or None

```

**示例#1 :** 在这些示例中，我们展示了 urlObject.port()方法如何从主机名中提取 url 的端口号。

```
// Importing the module 'url' 
const url = require('url'); 

var adr = 
'http://localhost:8080/default.htm?year=2019&month=may'; 

// Parse the address: 
var q = url.parse(adr, true); 

/* The parse method returns an object containing 
URL properties */

console.log(q.port); 
```

**输出:**

```
8080

```

**例 2 :**

```
// Importing the module 'url' 
const url = require('url'); 

var adr = 
'http://localhost/default.htm?year=2019&month=may'; 

// Parse the address: 
var q = url.parse(adr, true); 

/* The parse method returns an object containing 
URL properties */

console.log(q.port); 
```

**输出:**

```
null

```