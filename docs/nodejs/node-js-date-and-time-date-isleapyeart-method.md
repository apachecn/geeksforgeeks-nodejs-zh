# Node.js 日期时间 Date.isLeapYeart()方法

> 原文:[https://www . geesforgeks . org/node-js-date-time-date-islapyeart-method/](https://www.geeksforgeeks.org/node-js-date-and-time-date-isleapyeart-method/)

**日期和时间。date . isleappyear()**是一个用于操作 JS 日期和时间模块的极简函数集合，用于检查给定的年份是否是闰年。

**所需模块:**由 npm 安装模块或在本地使用。

**通过使用 npm:**

```js
npm install date-and-time --save
```

**通过使用 CDN 链接:**

```js
<script src="/path/to/date-and-time.min.js"></script>
```

**语法:**

```js
const isLeapYear(y)
```

**参数:**此法取一串年。

**返回值:**当且仅当年份字符串为 leap 时，此方法返回布尔值 true。

**例 1:**

## index . js

```js
// Node.js program to demonstrate the  
// Date.isLeapYear() method

// Importing http module
const date = require('date-and-time')

// creating object of current date and time 
// by using Date() 
const now  =  new Date();

// Checking the year is leap or not
// by using date.isLeapYear() api
const value = date.isLeapYear(now.getFullYear());

// display the result
if(value)
    console.log("This is a leap year")
else
    console.log("This is not a leap year")
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
This is not a leap year
```

**例 2:**

## index . js

```js
// Node.js program to demonstrate the  
// Date.isLeapYear() method

// Importing http module
const date = require('date-and-time')

// Creating object of current date and time 
// by using Date() method
const now  =  new Date();

now.setFullYear(2016)

// Checking the year leap or not
// by using date.isLeapYear() api
const value = date.isLeapYear(now.getFullYear());

// Display the result
if(value)
    console.log("This is a leap year")
else
    console.log("This is not a leap year")
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
This is a leap year
```

**参考:**T2】https://github.com/knowledgecode/date-and-time#isleapyeary