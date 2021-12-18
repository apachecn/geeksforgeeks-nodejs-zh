# 如何在 Node.js 中不尾随换行符打印控制台？

> 原文:[https://www . geesforgeks . org/how-print-console-不带尾随-newline-in-node-js/](https://www.geeksforgeeks.org/how-to-print-console-without-trailing-newline-in-node-js/)

在 Node.js 中， [console.log()方法](https://www.geeksforgeeks.org/node-js-console-log-function/)用于在控制台上显示消息。默认情况下，console.log()方法在控制台上打印，并带有尾随换行符。

**例 1:**

```
// Node.js program to demonstrate the   
// console.log() Method

console.log("Welcome to GeeksforGeeks! ");
console.log("A computer science portal for geeks");
```

**输出:**

```
Welcome to GeeksforGeeks!
A computer science portal for geeks
```

在上例中，*欢迎来到 GeeksforGeeks！第一行印着*，第二行印着*极客计算机科学门户网站*。
但有时我们可能需要打印不带换行符的控制台。在这种情况下，我们可以使用 [process.stdout.write()](https://nodejs.org/api/process.html#process_process_stdout) 方法打印到控制台，而不用尾随换行符。

**例 2:**

```
// Node.js program to demonstrate the   
// process.stdout.write() Method

process.stdout.write("Welcome to GeeksforGeeks! ");
process.stdout.write("A computer science portal for geeks");
```

**输出:**

```
Welcome to GeeksforGeeks! A computer science portal for geeks
```

**注意:**流程对象是全局的，所以不用 [require()](https://nodejs.org/en/knowledge/getting-started/what-is-require/) 方法就可以使用。