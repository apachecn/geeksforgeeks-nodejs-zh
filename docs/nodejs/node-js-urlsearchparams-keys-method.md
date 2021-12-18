# node . js URL searcheparams . keys()方法

> 原文:[https://www . geesforgeks . org/node-js-urlsearchprams-keys-method/](https://www.geeksforgeeks.org/node-js-urlsearchparams-keys-method/)

**urlSearchParams.keys()** 方法是 **url** 模块中 **URLSearchParams** 类的内置应用编程接口，用于获取只包含 urlSearchParams 对象的所有名称条目的迭代器对象。

**语法:**

```
const urlSearchParams.keys()
```

**参数:**此方法不接受任何参数。

**返回值:**此方法返回只包含 URL 搜索参数对象的所有名称条目的迭代器对象。

下面的程序说明了 Node.js 中**方法的使用:**

**示例 1:** **文件名:app.js**

```
// Node.js program to demonstrate the 
// URLSearchParams.keys() method

// Importing the 'url' module
const http = require('url');

// Creating and initializing 
// URLSearchParams object
const params = new URLSearchParams();

// Appending value in the object
params.append('A', 'Book');
params.append('B', 'Pen');
params.append('C', 'Pencile');

// Getting all the name entries only
// by using keys() API
const iterator = params.keys();

// Display result for each name entry
console.log("list of all the keys");
for (const [name] of iterator) {
    console.log(name);
}
```

使用以下命令运行 **app.js** 文件:

```
node app.js
```

**输出:**

```
list of all the keys
A
B
C

```

**示例 2:**
**文件名:app.js**

```
// Node.js program to demonstrate the 
// URLSearchParams.keys() method

// Importing the module 'url'
const http = require('url');

// Creating and initializing
// URLSearchParams object
const params = new URLSearchParams();

// Appending value in the object
params.append('G', '1');
params.append('F', '2');
params.append('G', '3');

// Getting all the name entries only
// by using keys() api
const iterator = params.keys();

// Display result for each name entry
console.log("list of all the keys");
for (const [name] of iterator) {
    console.log(name);
}
```

使用以下命令运行 **app.js** 文件:

```
node app.js
```

**输出:**

```
list of all the keys
G
F
G

```

**注意:**以上程序不会在在线 JavaScript 和脚本编辑器上运行。

**参考:**[https://nodejs . org/dist/latest-v 14 . x/docs/API/URL . html # URL _ urlsearchprams _ keys](https://nodejs.org/dist/latest-v14.x/docs/api/url.html#url_urlsearchparams_keys)