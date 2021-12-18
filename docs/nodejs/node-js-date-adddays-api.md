# node . js date . add days()API

> 原文:[https://www.geeksforgeeks.org/node-js-date-adddays-api/](https://www.geeksforgeeks.org/node-js-date-adddays-api/)

**日期和时间。Date.addDays()** 是操作 JS 日期和时间模块的极简函数集合，用于将额外的 Days 添加到现有的日期和时间。

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
addDays(dateObj, days)
```

**参数**:该方法以下列参数为参数:

*   **dateobject:** is a string object of date.
*   **Day:** is the number of days.

**返回值**:此方法返回更新的日期和时间。

**例 1:**

## index . js

```
// Node.js program to demonstrate the  
// Date.addDays() method

// Importing module
const date = require('date-and-time')

// Creating object of current date and time 
// by using Date() 
const now = new Date();

// Adding Days to the existing date and time
// by using date.addDays() method
const value = date.addDays(now, 24);

// Display the result
console.log("updated date and time : " + value)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
updated date and time :
Wed Mar 31 2021 20:07:07 GMT+0530 (India Standard Time)
```

**例 2:**

## index . js

```
// Node.js program to demonstrate the  
// Date.addDays() method

// Importing module
const date = require('date-and-time')

// Creating object of current date and time 
// by using Date() 
const now = new Date();

now.setDate(20)

// Adding Days to the existing date and time
// by using date.addDays() method
const value = date.addDays(now, 24);

// Display the result
console.log("updated date and time : " + value)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
updated date and time : 
Tue Apr 13 2021 20:09:57 GMT+0530 (India Standard Time)
```

**参考:**[https://github . com/knowledge code/date-time # adddaysdateobj-days](https://github.com/knowledgecode/date-and-time#adddaysdateobj-days)