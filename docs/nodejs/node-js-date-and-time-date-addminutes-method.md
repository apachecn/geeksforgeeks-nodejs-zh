# Node.js 日期时间 Date.addMinutes()方法

> 原文:[https://www . geesforgeks . org/node-js-date-time-date-addminutes-method/](https://www.geeksforgeeks.org/node-js-date-and-time-date-addminutes-method/)

**日期和时间。Date.addMinutes()** 方法用于将额外的分钟添加到现有的日期和时间。

**所需模块:**由 npm 安装模块或在本地使用。

*   **By using NPM: 【T1]**

```
npm install date-and-time --save
```

*   **By using CDN link:**

```
<script src="/path/to/date-and-time.min.js"></script>
```

**语法:**

```
const addMinutes(dateObj, minutes)
```

**参数:** 该方法以下列参数为参数:

*   **dateobject:** is a string object of date.
*   **Minutes:** is the number of minutes to be added.

**返回值:**此方法返回更新的日期和时间。

**例 1:**

## index . js

```
// Node.js program to demonstrate the  
// Date.addMinutes() method

// Importing date-and-time module
const date = require('date-and-time')

// Creating object of current date and time 
// by using Date() 
const now  =  new Date();

// Adding Minutes to the existing
// date and time by using
//date.addMinutes() method
const value = date.addMinutes(now,24);

// Display the result
console.log("updated date and time :- " + value)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

> 更新日期和时间:-Fri 2021 年 3 月 19 日 18:38:26 GMT+0530(印度标准时间)

**例 2:**

## index . js

```
// Node.js program to demonstrate the  
// Date.addMinutes() method

// Importing date-and-time module
const date = require('date-and-time')

// Creating object of current date and time 
// by using Date() 
const now  =  new Date();

now.setDate(20)

// Adding Minutes to the existing date and time
// by using date.addMinutes() method
const value = date.addMinutes(now,30);

// Display the result
console.log("updated date and time :- " + value)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

> 更新日期和时间:-2021 年 3 月 20 日星期六 18:04:43 GMT+0530(印度标准时间)

**参考**:[https://github . com/knowledge code/date-time # addminutes data object-minutes](https://github.com/knowledgecode/date-and-time#addminutesdateobj-minutes)