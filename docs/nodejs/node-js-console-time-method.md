# Node.js console.time()方法

> 原文:[https://www.geeksforgeeks.org/node-js-console-time-method/](https://www.geeksforgeeks.org/node-js-console-time-method/)

**console.time()方法**是 Node.js 的控制台类，用于启动一个计时器，该计时器用于计算一段代码或函数所花费的时间。方法 **console.timeEnd()** 用于停止计时器，并将经过的时间(以毫秒为单位)输出到 stdout。计时器可以精确到亚毫秒。

**语法**

```js
console.time( label )
```

**参数:**该方法接受单个参数**标签**作为参数可以在方法中传递，如果标签没有传递*默认*标签自动给方法。对于不同的功能或代码段，标签可以不同。

以下示例说明了 Node.js 中 **console.time()** 方法的工作原理:

**例 1:**

```js
// Node.js program to demonstrate the
// console.time() method

// Sample function
function addCount() {
  // Variable declaration
  var sum = 0;

  for (var i = 1; i < 100000; i++) {
    // Adding i to the sum variable
    sum += i;
  }

  // Return sum value
  return sum;
}

// Starts the timer
console.time();

// Function call
addCount();

// Ends the timer and print the time
// taken by the piece of code
console.timeEnd();
```

**输出:**

```js
default: 8.760ms
```

**例 2:**

```js
// Node.js program to demonstrate the
// console.time() method

// Sample function
function addCount() {
  // Variable declaration
  var sum = 0;
  for (var i = 1; i < 100000; i++) {
    // Adding i to the sum variable
    sum += i;
  }
  return sum; // returning sum
}

var timetaken = "Time taken by addCount function";

// Starts the timer. The label value is timetaken
console.time(timetaken);

addCount(); // function call

// Ends the timer and print the time
// taken by the piece of code
console.timeEnd(timetaken);
```

**输出:**

```js
Time taken by addCount function: 7.380ms
```

**示例 3:** 该示例同时对不同的功能使用不同的标签。

```js
// Node.js program to demonstrate the
// console.time() method

// Sample function
function addCount() {
  var sum = 0; // Variable declaration
  for (var i = 1; i < 100000; i++) {
    sum += i; // Adding i to the sum variable
  }
  return sum; // returning sum
}

function countTime() {
  var timetaken = "Time taken by addCount function";

  // Starts the timer, the label value is timetaken
  console.time(timetaken);

  console.log(addCount()); // function call

  // Ends the timer and print the time
  // taken by the piece of code
  console.timeEnd(timetaken);
}

var label2 = "Time taken by countTime function";

// Starts the timer, the label value is label2
console.time(label2);

countTime(); // function call

// Ends the timer and print the time
// taken by the piece of code
console.timeEnd(label2);
```

**输出:**

```js
4999950000
Time taken by addCount function: 24.884ms
Time taken by countTime function: 25.928ms
```

**参考:**T2【https://nodejs . org/docs/latest-v 11 . x/API/console . html # console _ console _ time _ label