# Node.js 日期时间 Date.transform()方法

> 原文:[https://www . geesforgeks . org/node-js-date-time-date-transform-method/](https://www.geeksforgeeks.org/node-js-date-and-time-date-transform-method/)

**日期和时间。Date.transform()** 方法用于将日期和时间从现有的字符串格式转换为新的字符串格式。

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
const transform(dateString, arg1, arg2[, utc])
```

**参数:**该 API 采用以下参数作为参数。

*   **Date string:** The date of the string object.
*   **arg1:** Existing string format.
*   **arg2:** New string format.

**返回值:**这个方法返回一个格式化字符串。

**例 1:**

## index . js

```js
// Node.js program to demonstrate the  
// Date.transform() method

// Importing http module
const date = require('date-and-time')

// Creating object of current date and time 
// by using Datw() 
const now  =  new Date(07-03-2021);

// Changing the format of date and time
// by using date.transform() api
const value = date.transform(
    now.toLocaleDateString(),
    'D/M/YYYY', 'YYYY/M/D');

// Display the result
console.log("transformed date and time :- "
     + value)
```

**输出:**

```js
transformed date and time :- 1970/1/1
```

**例 2:**

## index . js

```js
// Node.js program to demonstrate the  
// Date.transform() method

// Importing http module
const date = require('date-and-time')

// Changing the format of date and time
// by using date.transform() api
const value = date.transform(
    '23:14:05 GMT+0900',
    'HH:mm:ss [GMT]Z', 'YYYY/M/D');

// Display the result
console.log("transformed date and time :- "
      + value)
```

**输出:**

```js
transformed date and time :- 1970/1/1
```

**参考:**[https://github . com/knowledge code/date-time # transformdatestring-arg 1-arg 2-utc](https://github.com/knowledgecode/date-and-time#transformdatestring-arg1-arg2-utc)