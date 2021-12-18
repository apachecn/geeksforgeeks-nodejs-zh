# Node.js 日期时间 date .减法()方法

> 原文:[https://www . geesforgeks . org/node-js-date-time-date-减法-method/](https://www.geeksforgeeks.org/node-js-date-and-time-date-subtract-method/)

**日期时间 date .减法()**方法用于减去两个日期对象。

**所需模块**:由 npm 安装模块或在本地使用。

*   **By using npm.**

```js
npm install date-and-time --save
```

*   **By using CDN link.**

```js
<script src="/path/to/date-and-time.min.js"></script>
```

**语法:**

```js
const subtract(date1, date2)
```

**参数:** 该方法以下列参数为参数:

*   **date1:** is the first date object minus the second date.
*   **Date 2:** is the second date object.

**返回值:**此方法返回从日期 1 中减去日期 2 的结果对象。

**例 1:**

## index . js

```js
// Node.js program to demonstrate the  
// Date.subtract() method

// Importing date-and-time module
const date = require('date-and-time')

// Creating object of current date and time 
// by using Date() 
const now  =  new Date();

// Creating object of given date and time
const date1 = new Date(2015, 0, 1);

// Subtracting the both dates
// by using date.subtract() method
const value = date.subtract(now,date1);

// Display the result
console.log("total days between them " 
   + value.toDays())
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
total days between them 2270.3951833333335
```

**例 2:**

## index . js

```js
// Node.js program to demonstrate the  
// Date.subtract() method

// Importing date-and-time module
const date = require('date-and-time')

// Creating object of current date and time 
// by using Date() 
const now  =  new Date();

// Setting days in the existing date
now.setDate(20);

// Creating object of given date and time
const date1 = new Date(2015, 0, 1);

// Subtracting the both dates
// by using date.subtract() method
const value = date.subtract(now,date1);

// Display the result
console.log("total days between them " + value.toDays())
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
total days between them 2270.397227997685
```

**参考**:[https://github . com/knowledge code/日期和时间#减法日期 1-日期 2](https://github.com/knowledgecode/date-and-time#subtractdate1-date2)