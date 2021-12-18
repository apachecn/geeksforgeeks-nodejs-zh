# node . js . date . compile()API

> 原文:[https://www.geeksforgeeks.org/node-js-date-compile-api/](https://www.geeksforgeeks.org/node-js-date-compile-api/)

**日期和时间。Date.compile()** 是操作 JS 日期和时间模块的极简函数集合，用于为解析器编译格式字符串。

**所需模块:**由 npm 安装模块或在本地使用。

*   By using npm.

```
npm install date-and-time --save
```

*   Use CDN link.

```
<script src="/path/to/date-and-time.min.js"></script>
```

**语法:**

```
compile(formatString)
```

**参数:**该方法以格式字符串为参数。

**返回值**:该方法返回格式化的字符串日期。

**例 1:**

## index . js

```
// Node.js program to demonstrate the  
// Date.compile() method

// Importing http module
const date = require('date-and-time')

// Creating object of current date and time 
// by using Date() 
const now  =  new Date('07-03-2021');

// Getting pattern for the future use
// by using date.compile() method
const pattern = date.compile('D/M/YYYY');

// Getting formatted date and time 
// by using format() method
const value = date.format(now,pattern)

// Display the result
console.log("Formatted date and time : " + value)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Formatted date and time : 1/1/1970
```

**例 2:**

## index . js

```
// Node.js program to demonstrate the  
// Date.compile() method

// Importing module
const date = require('date-and-time')

// Creating object of current date and time 
// by using Datw() 
const now = new Date('07-03-2021');

// Getting pattern for the future use
// by using date.compile() method
const pattern = date.compile('M/D/YYYY');

// Parsing the date and time
// by using date.parse() method
const value = date.parse(now.toLocaleDateString(), pattern);

// Display the result
console.log("Formatted date and time: " + value)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Formatted date and time: 
Sat Jul 03 2021 00:00:00 GMT+0530 (India Standard Time)
```

**参考**:[https://github.com/knowledgecode/date-and-time](https://github.com/knowledgecode/date-and-time)