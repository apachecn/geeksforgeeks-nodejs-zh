# Node.js console.log()函数

> 原文:[https://www.geeksforgeeks.org/node-js-console-log-function/](https://www.geeksforgeeks.org/node-js-console-log-function/)

[Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 控制台类的**控制台. log()功能**用于显示控制台上的消息。它用换行符打印到 stdout。

**语法:**

```
console.log( [data][, ...] )

```

**参数:**该功能包含多个要打印的参数。

**返回类型:**函数返回传递的参数。

下面的程序演示了 console.log()函数的工作原理:

**程序 1:**

```
function GFG(name) {
     console.log("hello " + name);
}

// when parameters are passed
GFG("Geeksforgeeks");
```

**输出:**
![](img/1143d168312323b543f4c093e6494f12.png)

**程序 2:**

```
function GFG(name) {
     console.log("hello " + name);
}

// No parameters are passed
GFG();
```

**输出:**
![](img/c13690113b2763a820f8af23efe61941.png)