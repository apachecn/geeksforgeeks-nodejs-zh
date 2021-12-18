# Node.js console.timeEnd()方法

> 原文:[https://www . geesforgeks . org/node-js-console-time end-method/](https://www.geeksforgeeks.org/node-js-console-timeend-method/)

**console.timeEnd()方法**是 Node.js 的控制台类，该方法停止之前使用 **console.time()** 方法启动的定时器，并使用 stdout 显示结果。

**语法:**

```
console.timeEnd( label )
```

**参数:**该方法接受一个保存字符串值的单参数**标签**。如果标签没有通过，即标签的值是*默认的*，那么它自动给方法。对于不同的功能或代码段，标签可以不同。

**返回值:**此方法显示标签和一段代码所花费的时间。

以下示例说明了 Node.js 中的 **console.timeEnd()方法**:

**例 1:**

```
// Node.js program to demonstrate the
// console.timeEnd() method

// Sample function
function addCount() {
  var sum = 0; // Variable declaration
  for (var i = 1; i < 100000; i++) {
    sum += i; // Adding i to the sum variable
  }
  return sum; // Return sum value
}

// Starts the timer, here default label is used
console.time();

addCount(); // function call

// Ends the timer and print the time
// taken by the piece of code
console.timeEnd();
```

**输出:**

```
default: 7.517ms
```

**例 2:**

```
// Node.js program to demonstrate the
// console.timeEnd() method

// Sample function
function addCount() {
  var sum = 0; // Variable declaration
  for (var i = 1; i < 100000; i++) {
    sum += i; // Adding i to the sum variable
  }
  return sum; // Return sum value
}

var timetaken = "Time taken by addCount function";

// Starts the timer, the label value is timetaken
console.time(timetaken);

addCount(); // function call

// Ends the timer and print the time
// taken by the piece of code
console.timeEnd(timetaken);
```

**输出:**

```
Time taken by addCount function: 8.972ms
```

**参考:**T2【https://nodejs . org/docs/latest-v 11 . x/API/console . html # console _ console _ time end _ label