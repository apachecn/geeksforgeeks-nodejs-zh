# Node.js Date.format() API

> 原文:[https://www.geeksforgeeks.org/node-js-date-format-api/](https://www.geeksforgeeks.org/node-js-date-format-api/)

**日期和时间。Date.format()** 是操作 JS 日期和时间模块的极简函数集合，用于按照一定的模式格式化日期。

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
format(dateObj, formatString[, utc])
```

**参数**:该方法以下列参数为参数:

*   **dateobj:** is the object of date.
*   **Format string:** is a new string format for displaying date.

**返回值:**此方法返回格式化的日期和时间。

**例 1:**

## index . js

```js
// Node.js program to demonstrate the  
// Date.format() method

// Importing module
const date = require('date-and-time')

// Creating object of current date and time 
// by using Date() 
const now  =  new Date();

// Formating the date and time
// by using date.format() method
const value = date.format(now,'YYYY/MM/DD HH:mm:ss');

// Display the result
console.log("current date and time : " + value)
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
current date and time : 2021/03/07 12:13:46
```

**例 2:**

## index . js

```js
// Node.js program to demonstrate the  
// Date.format() method

// Importing module
const date = require('date-and-time')

// Formatting the date and time
// by using date.format() method
const value = date.format((new Date('December 17, 1995 03:24:00')),
  'YYYY/MM/DD HH:mm:ss');

// Display the result
console.log("date and time : " + value)
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
date and time : 1995/12/17 03:24:00
```

**参考**:[https://github.com/knowledgecode/date-and-time](https://github.com/knowledgecode/date-and-time)