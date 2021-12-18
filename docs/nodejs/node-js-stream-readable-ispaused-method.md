# node . js Stream readable . isposed()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-readable-is paused-method/](https://www.geeksforgeeks.org/node-js-stream-readable-ispaused-method/)

**readable . isposed()方法**是 Stream 模块的内置应用编程接口，用于检查 Readable 流的当前操作状态。

**语法:**

```js
readable.isPaused()
```

**参数:**此方法不接受任何参数。

**返回值:**如果可读状态暂停，则返回真，否则返回假。

以下示例说明了在 Node.js 中使用**readable . isposed()方法**:

**例 1:**

```js
// Node.js program to demonstrate the     
// readable.isPaused() method  

// Include stream module
const stream = require('stream');

// Constructing readable stream
const readable = new stream.Readable();

// Calling isPaused method
readable.isPaused();
```

**输出:**

```js
false

```

**例 2:**

```js
// Node.js program to demonstrate the     
// readable.isPaused() method  

// Include stream module
const stream = require('stream');

// Constructing readable stream
const readable = new stream.Readable();

// Calling isPaused method
readable.isPaused();

// Calling the pause() function
// to pause readable state
readable.pause();

// Again calling isPaused to check
// if its paued or not
readable.isPaused();
```

**输出:**

```js
true
```

**参考:**T2】https://nodejs.org/api/stream.html#stream_readable_ispaused