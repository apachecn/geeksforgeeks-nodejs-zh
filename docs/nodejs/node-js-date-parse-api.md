# node . js date . parse()API

> 原文:[https://www.geeksforgeeks.org/node-js-date-parse-api/](https://www.geeksforgeeks.org/node-js-date-parse-api/)

**日期和时间。Date.parse()** 是操作 JS 日期和时间模块的极简函数集合，用于按照一定的模式解析日期。

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
parse(dateString, arg)
```

**参数**:该方法以下列参数为参数:

*   **Date string:** is a date string object.
*   **arg:** is the required date format.

**返回值:**该方法返回解析后的日期和时间。

**例 1:**

## index . js

```js
// Node.js program to demonstrate the  
// Date.parse() method

// Importing module
const date = require('date-and-time')

// Creating object of current date and time 
// by using Date() 
const now  =  new Date('07-03-2021');

// Parsing the date and time
// by using date.parse() method
const value = date.parse(now.toLocaleDateString(),'D/M/YYYY');

// Display the result
console.log("parsed date and time : " + value)
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
parsed date and time :
Thu Jan 01 1970 00:00:00 GMT+0530 (India Standard Time)
```

**例 2:**

## index . js

```js
// Node.js program to demonstrate the  
// Date.parse() method

// Importing module
const date = require('date-and-time')

// Parsing the date and time
// by using date.parse() method
const value = date.parse('23:14:05 GMT+0900','HH:mm:ss [GMT]Z');

// Display the result
console.log("Parsed date and time : " + value)
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Parsed date and time :
Thu Jan 01 1970 19:44:05 GMT+0530 (India Standard Time)
```

**参考**:[https://github.com/knowledgecode/date-and-time](https://github.com/knowledgecode/date-and-time)