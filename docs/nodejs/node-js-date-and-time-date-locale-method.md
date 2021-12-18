# Node.js 日期时间 Date.locale()方法

> 原文:[https://www . geesforgeks . org/node-js-date-time-date-locale-method/](https://www.geeksforgeeks.org/node-js-date-and-time-date-locale-method/)

**日期和时间。Date.locale()** 方法用于获取区域设置或将区域设置从一种语言切换到另一种语言。

**所需模块**:由 npm 安装模块或在本地使用。

**通过使用 npm:**

```
npm install date-and-time --save
```

**通过使用 CDN 链接:**

```
<script src="/path/to/date-and-time.min.js"></script>
```

**语法:**

```
locale(])
```

**参数**:该方法以地区和代码为参数。

**返回值**:该方法返回日期时间对象的当前区域设置。

**例 1:**

## index . js

```
// Node.js program to demonstrate the  
// Date.locale() APi

// Importing date-and-time module
const date = require('date-and-time')

// Getting the locale value
const value = date.locale();

// display the result
console.log("current locale :- " + value)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
current locale :- en
```

**示例 2:更改地区**

**文件名:index . js**

## index . js

```
// Node.js program to demonstrate the  
// Date.locale() APi

// Importing date-and-time module
const date = require('date-and-time')

// Changing the local to es spanish
console.log("Change local "+date.locale('es'))
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Change local es
```

**参考**:[https://github . com/knowledge code/date-time # locale code-locale](https://github.com/knowledgecode/date-and-time#localecode-locale)