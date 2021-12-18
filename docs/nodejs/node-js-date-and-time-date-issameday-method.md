# Node.js 日期时间 Date.isSameDay()方法

> 原文:[https://www . geesforgeks . org/node-js-date-time-date-issameday-method/](https://www.geeksforgeeks.org/node-js-date-and-time-date-issameday-method/)

**日期和时间。Date.isSameDay()** 方法用于检查给定日期是否相同。

**所需模块**:由 npm 安装模块或在本地使用。

*   **By using NPM: 【T1]**

```js
npm install date-and-time --save
```

*   **By using CDN link:**

```js
<script src="/path/to/date-and-time.min.js"></script>
```

**语法:**

```js
isSameDay(date1, date2)
```

**参数:**该方法取以下参数-

*   **Date 1:** Save the object of date 1.
*   **Date2:** It saves the object of Date2.

**返回值:**当且仅当两个日期相同时，该方法返回布尔值 true。

**例 1:**

## index . js

```js
// Node.js program to demonstrate the  
// Date.isSameDay() APi

// Importing http module
const date = require('date-and-time')

// Creating object of current date
// and time by using Date() 
const now1  =  new Date();

// Creating object of current date 
// and time using Date() method
const now2  =  new Date();

// Checking if both dates are same or not
// by using date.isSameDay() api
const value = date.isSameDay(now1,now2);

// Display the result
if(value)
    console.log("Both dates are same")
else
    console.log("Both dates are not same")
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

**输出:**

```js
Both dates are same
```

**例二:**

## Javascript

```js
// Node.js program to demonstrate the  
// Date.isSameDay() APi

// Importing http module
const date = require('date-and-time')

// Creating object of current date 
// and time using Date() method
const now1  =  new Date();

// Creating object of current date and time 
// by using Date() method
const now2  =  new Date();

now1.setFullYear(2016)

// Checking if both dates are same or not
// by using date.isSameDay() method
const value = date.isSameDay(now1,now2);

// Display the result
if(value)
    console.log("Both dates are same")
else
    console.log("Both dates are not same")
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

**输出:**

```js
Both dates are not same
```

**参考:**[https://github . com/knowledge code/date-time # issamedaydate 1-date 2](https://github.com/knowledgecode/date-and-time#issamedaydate1-date2)