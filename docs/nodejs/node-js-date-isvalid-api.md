# Node.js Date.isValid() API

> 原文:[https://www.geeksforgeeks.org/node-js-date-isvalid-api/](https://www.geeksforgeeks.org/node-js-date-isvalid-api/)

**日期和时间。Date.isValid()** 是一个极简的函数集合，用于操作 JS 日期和时间模块，该模块用于用字符串格式验证特定的日期和时间。

**所需模块:**由 npm 安装模块或在本地使用。

*   By using npm.

```js
npm install date-and-time --save
```

*   Use CDN link.

```js
<script src="/path/to/date-and-time.min.js"></script>
```

**语法:**

```js
isValid(arg1[, arg2])
```

**参数:**该方法以下列参数为参数:

*   **arg1:** is a date-time object.
*   **arg2:** is a string format of a given date.

**返回值:**当且仅当条款有效时，此方法返回真。

**例 1:**

## index . js

```js
// Node.js program to demonstrate the  
// Date.isValid() method

// Importing date-and-time module
const date = require('date-and-time')

// Parsing the date and time
// by using date.parse() method
const status = date.isValid('29-02-2015', 'DD-MM-YYYY');

// Display the result
if(status)
  console.log("Date is valid")
else
  console.log("Date is not invalid")
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Date is not invalid
```

**例 2:**

## index . js

```js
// Node.js program to demonstrate the  
// Date.isValid() method

// Importing date-and-time module
const date = require('date-and-time')

// Pre parsing the date and time
// by using preparse() method
const result = date.preparse('2015/01/02 23:14:05', 'YYYY/MM/DD HH:mm:ss');

// Validating the terms
// by using date.isValid() method
const status = date.isValid(result);

// Display the result
if(status)
  console.log("Date is valid")
else
  console.log("Date is not invalid")
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Date is valid
```

**参考:**T2】https://github.com/knowledgecode/date-and-time