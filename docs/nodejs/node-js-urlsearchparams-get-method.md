# node . js urlsearchprams . get()方法

> 原文:[https://www . geesforgeks . org/node-js-urlsearchparams-get-method/](https://www.geeksforgeeks.org/node-js-urlsearchparams-get-method/)

**urlSearchParams.get()** 方法是 **url** 模块中类 **urlSearchParams** 的内置应用程序编程接口，用于获取存在于 URL 搜索参数对象中的特定名称条目的值。

**语法:**

```
const urlSearchParams.get( name )
```

**参数:**该方法以名称作为参数。

**返回值:**该方法返回 url 搜索参数对象中存在的特定名称条目的值。

下面的程序说明了在 Node.js 中**urlsearchprams . get()**方法的使用:

**示例 1:** **文件名:app.js**

```
// Node.js program to demonstrate the 
// URLSearchParams.get() method

// Importing the module 'url'
const http = require('url');

// Creating and initializing 
// URLSearchParams object
const params = new URLSearchParams();

// Appending value in the object
params.append('A', 'Book');
params.append('B', 'Pen');
params.append('C', 'Pencile');

// Getting the value for entry 'A'
// by using get() api
const value = params.get('A');

// Display the result
console.log("value for A is " + value);
```

使用以下命令运行 **app.js** 文件:

```
node app.js
```

**输出:**

```
value for A is Book

```

**示例 2:** **文件名:app.js**

```
// Node.js program to demonstrate the 
// URLSearchParams.get() method 

// Importing the module 'url'
const http = require('url');

// Creating and initializing
// URLSearchParams object
const params = new URLSearchParams();

// Appending value in the object
params.append('A', 'Book');
params.append('B', 'Pen');
params.append('C', 'Pencile');

// Getting the value for entry 'A'
// by using get() api
const value = params.get('a');

// Display the result
console.log("value for a is " + value);
```

使用以下命令运行 **app.js** 文件:

```
node app.js
```

**输出:**

```
value for a is null

```

**参考:**[https://nodejs . org/dist/latest-v 14 . x/docs/API/URL . html # URL _ urlsearchprams _ get _ name](https://nodejs.org/dist/latest-v14.x/docs/api/url.html#url_urlsearchparams_get_name)