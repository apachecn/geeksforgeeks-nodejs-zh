# Node.js urlObject.href API

> 原文:[https://www.geeksforgeeks.org/node-js-urlobject-href-api/](https://www.geeksforgeeks.org/node-js-urlobject-href-api/)

urlObject.href API 用于返回完整的 URL 字符串以及协议(HTTP)和路径名或其他搜索项。

**语法**

```
urlObject.href
```

```
For example: 'http://www.geeksforgeeks.com/login/password.html'

Here, Protocol = http
      Path = /login
      Host = 'www'
      File Name = password.html

```

下面的程序说明了**方法在 Node.js 中的使用:**

**例 1:**

```
// Node program to demonstrate the 
// urlObject.href API as Setter

// It will return a URL object
const gfg = new URL('https://www.geeksforgeeks.com/login.html '); 

// Output the fetched url
console.log(gfg.href); 
```

**输出:**

```
 https://www.geeksforgeeks.com/login.html
```

**例 2:**

```
// Node program to demonstrate the  
// url.href API as Setter

// Importing the module 'url-parse'

// Use command 'npm install url-parse' in command
// prompt to import this module
var parse = require('url-parse'); 

var url = parse('https://www.example.com:777/a/b?c=d&e=f#g ');

console.log(url.href);
```

**输出:**

```
 https://www.example.com:777/a/b?c=d&e=f#g 
```

**注意:**以上程序将使用**节点 app.js** 命令编译运行。

**参考:**[https://nodejs . org/API/URL . html # URL _ URL object _ href](https://nodejs.org/api/url.html#url_urlobject_href)