# node . js date . add hours()API

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-date-add hours-API/

**日期和时间。Date.addHours()** 是操作 JS 日期和时间模块的极简函数集合，用于将额外的 Hours 添加到现有的日期和时间。

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
addHours(dateObj, months)
```

**参数**:该方法以下列参数为参数:

*   **dateobject:** is a string object of date.
*   **Hours:** is the number of hours.

**返回值**:此方法返回更新的日期和时间。

**例 1:**

## index . js

```js
// Node.js program to demonstrate the  
// Date.addHours() method

// Importing module
const date = require('date-and-time')

// Creating object of current date and time 
// by using Date() 
const now  =  new Date();

// Adding Hours to the existing date and time
// by using date.addHours() method
const value = date.addHours(now,24);

// Display the result
console.log("updated date and time : " + value)
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
updated date and time :
Mon Mar 08 2021 20:35:37 GMT+0530 (India Standard Time)
```

**例 2:**

## index . js

```js
// Node.js program to demonstrate the  
// Date.addHours() method

// Importing module
const date = require('date-and-time')

// Creating object of current date and time 
// by using Date() 
const now = new Date();

now.setDate(20)

// Adding Hours to the existing date and time
// by using date.addHours() method
const value = date.addHours(now, 30);

// Display the result
console.log("updated date and time : " + value)
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
updated date and time :
Mon Mar 22 2021 02:37:29 GMT+0530 (India Standard Time)
```

**参考:**T2