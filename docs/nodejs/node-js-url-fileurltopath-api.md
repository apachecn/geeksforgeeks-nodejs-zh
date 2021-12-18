# node . js URL . file urltopath API

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-URL-file urltopath API/

此函数将文件 URL 解码为路径字符串，并确保在将给定文件 URL 转换为路径时，URL 控制字符(/，%)被正确追加/调整。

**语法:**

```js
url.fileURLToPath( url )
```

**参数:**该函数接受单参数 *url* ，保存要转换为路径的文件 url 字符串或对象。

**返回值:**返回一个字符串，代表完全解析的平台特定文件路径。

下面的程序说明了**方法在 Node.js 中的使用:**

**例 1:**

```js
// Node program to demonstrate the 
// URL.fileURLToPath() API as Setter

// Importing the module 'url' 
const url = require('url');

 // Some random path from system
const file = 'file://computerscience/geeksforgeeks.txt'

// Converting our file to properly encoded path                    
console.log(url.fileURLToPath(file)) 
```

**输出:**

```js
\\computerscience\geeksforgeeks.txt
```

**例 2:**

```js
// Node program to demonstrate the 
// URL.fileURLToPath() API as Setter

// Importing the module 'url' 
const url = require('url');

// Some random path from system
const file = 'file:///C:/path/example/gfg'

// Converting the file to properly encoded path
console.log(url.fileURLToPath(file))
```

**输出:**

```js
 C:\path\example\gfg 
```

**注意:**以上程序将使用**节点 app.js** 命令编译运行。

**参考:**[https://nodejs . org/API/URL . html # URL _ URL _ fileurltopath _ URL](https://nodejs.org/api/url.html#url_url_fileurltopath_url)