# node . js URL . pathtofileurl API

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-URL-pathtofileurl API/

此函数将路径转换为文件，并确保在将给定路径转换为文件 URL 时，URL 控制字符(/，\，: )被正确追加/调整。

**语法:**

```
url.pathToFileURL(path)
```

**参数:**该函数接受单参数**路径**，该路径保存转换文件网址的路径。

**返回值:**该函数返回文件 URL 对象。

以下程序说明了**网址的使用。-路径文件**方法:

**例 1:**

```
// Node program to demonstrate the  
// URL.pathToFileURL API as Setter

// Importing the module 'url' 
var url = require('url');

// Some random path from system
const path = 'D:\GeeksForGeeks'

// Converting the path to properly encoded file
console.log(url.pathToFileURL(path)) 
```

**输出:**

```

URL {
  href: 'file:///D:/GeeksForGeeks',
  origin: 'null',
  protocol: 'file:',
  username: '',
  password: '',
  host: '',
  hostname: '',
  port: '',
  pathname: '/D:/GeeksForGeeks',
  search: '',
  searchParams: URLSearchParams {},
  hash: ''
}

```

**例 2:**

```
// Node program to demonstrate the  
// URL.pathToFileURL API as Setter

// Importing the module 'url' 
var url = require('url');

// Some random path from system
const path = 'D:\NodeJS\node_modules\npm'

// Converting the path to properly encoded file
console.log(url.pathToFileURL(path)) 
```

**输出:**

```
URL {
  href: 'file:///D:/NodeJS%0Aode_modules%0Apm',
  origin: 'null',
  protocol: 'file:',
  username: '',
  password: '',
  host: '',
  hostname: '',
  port: '',
  pathname: '/D:/NodeJS%0Aode_modules%0Apm',
  search: '',
  searchParams: URLSearchParams {},
  hash: ''
}

```

**注意:**以上程序将使用**节点 app.js** 命令编译运行。

参考[https://nodejs . org/API/URL . html # URL _ URL _ pathtofileurl _ path](https://nodejs.org/api/url.html#url_url_pathtofileurl_path)