# Node.js console.warn()功能

> 原文:[https://www . geesforgeks . org/node-js-console-warn-function/](https://www.geeksforgeeks.org/node-js-console-warn-function/)

来自[节点](https://www.geeksforgeeks.org/introduction-to-nodejs/)控制台类的**控制台. warn()功能**用于在控制台上显示警告信息。它用换行符打印到 stderr。

**注意:**这个函数是 console.error()函数的别名。

**语法:**

```
console.warn( [data][, ...args] )
```

**参数:**该函数可以包含多个参数。第一个参数用于主要消息，其他参数用于替代值。

**返回值:**函数返回警告信息。

以下程序演示了 console.warn()功能的工作原理:

**节目 1:**

```
function displayWarning(x) {
    console.warn(`GeeksforGeeks is a ${x} portal`);
}

const x = 'Computer Science';

displayWarning(x);
```

**输出:**

```
GeeksforGeeks is a Computer Science portal
```

**节目 2:**

```
function compareNumber(x, y) {

    // Check condition
    if (x > y) {
        console.warn(`${x} is greater then ${y}`);
    }
    else {
        console.warn(`${x} is less then or equal to ${y}`);
    }
}

// Store number to variable
x = 100;
y = 50;

compareNumber(x, y);
```

**输出:**

```
100 is greater then 50
```