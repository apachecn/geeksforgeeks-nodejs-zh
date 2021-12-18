# Node.js stream.finished()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-finished-method/](https://www.geeksforgeeks.org/node-js-stream-finished-method/)

**stream.finished()方法**用于在某个流不再可写或可读时，或者在遇到错误或未成熟的关闭事件时接收警报。

**语法:**

```js
stream.finished(stream, options, callback)
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **流:**该参数可以可读也可以写。
*   **选项:**这是一个对象，可以是:
    1.  它可以是一个**错误**，也就是说，如果它被设置为假，那么发出事件的调用(' error '，err)不会被认为已经完成，默认情况下它是真的。
    2.  它可以是**可读的**，即如果它被设置为假，那么当流结束时调用回调函数，流仍然是可读的，默认情况下它是真的。
    3.  它可以是**可写的**，即当设置为假时，然后调用回调函数，当流结束时，流仍然可以是可写的，并且默认为真。
*   **回调:**接受选择性错误参数的回调函数。

**返回值:**它返回一个清除函数，该函数分离所有注册的侦听器。
以下示例说明了 **stream.finished()方法**在 Node.js:
**示例 1:** 中的使用

## java 描述语言

```js
// Node.js program to demonstrate the     
// stream.finished(stream[, options], 
// callback) method

// Including fs module
var fs = require('fs');

// Constructing finished from stream
const { finished } = require('stream');

// Constructing promisify from
// util
const { promisify } = require('util');

// Defining finishedAsync method
const finishedAsync = promisify(finished);

// Constructing readable stream
const readable = fs.createReadStream("input.text");

// Constructing writable stream
var writable = fs.createWriteStream("output.text");

// Async function
(async function run() {
  try{ 

    // Calling pipe method
    readable.pipe(writable);
    await finishedAsync(readable);
    console.log("Readable is being consumed");

  }

  // Shows error
  catch(err) {
    console.error(err);
  }
  })();
```