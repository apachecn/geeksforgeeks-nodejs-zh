# Node.js 日期时间 date .add 毫秒()方法

> 原文:[https://www . geesforgeks . org/node-js-date-time-date-add 毫秒-method/](https://www.geeksforgeeks.org/node-js-date-and-time-date-addmilliseconds-method/)

**日期和时间 date and 毫秒()**方法用于将额外的毫秒添加到现有的日期和时间。

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
const addMilliseconds(dateObj, seconds)
```

**参数** : 该方法以下列参数为参数:

*   **dateobject:** is a string object of date.
*   **Seconds:** is the number of milliseconds to be added.

**返回值:**此方法返回更新的日期和时间。

**例 1:**

## index . js

```js
// Node.js program to demonstrate the  
// Date.addMilliseconds() method

// Importing date-and-time module
const date = require('date-and-time')

// Creating object of current date
// and time using Date() method
const now  =  new Date();

// Adding Milliseconds to the existing date and time
// by using date.addMilliseconds() method
const value = date.addMilliseconds(now,24);

// Display the result
console.log("updated date and time :- " + value)
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
updated date and time :- Fri Mar 19 2021 18:15:26 GMT+0530 (India Standard Time)
```

**例 2:**

## index . js

```js
// Node.js program to demonstrate the  
// Date.addMilliseconds() method

// Importing date-and-time module
const date = require('date-and-time')

// Creating object of current date 
// and time using Date() method
const now  =  new Date();

now.setDate(20)

// Adding Milliseconds to the existing
// date and time by using
// date.addMilliseconds() method
const value = date.addMilliseconds(now,30);

// Display the result
console.log("updated date and time :- " + value)
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
updated date and time :- Sat Mar 20 2021 18:16:05 GMT+0530 (India Standard Time)
```

**参考**:T2