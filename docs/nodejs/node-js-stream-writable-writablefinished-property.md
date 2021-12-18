# Node.js Stream 可写.可写成品属性

> 原文:[https://www . geesforgeks . org/node-js-stream-writteable-finished-property/](https://www.geeksforgeeks.org/node-js-stream-writable-writablefinished-property/)

在“完成”事件发出之前，立即将**可写.可写已完成属性**设置为真。

**语法:**

```
writable.writableFinished
```

**返回值:**如果在调用“完成”事件之前调用该事件，则返回真，否则返回假。
以下示例说明了在 Node.js 中使用**可写可写成品属性**:

**例 1:**

```
// Node.js program to demonstrate the     
// writable.writableFinished Property

// Accessing stream module
const stream = require('stream');

// Creating a stream and creating 
// a write function
const writable = new stream.Writable({

  // Write function with its 
  // parameters
  write: function(chunk, encoding, next) {

    // Converting the chunk of
    // data to string
    console.log(chunk.toString());
    next();
  }
});

// Using for loop and calling 
// write method 
for (let i = 0; i < 5; i++) {
  writable.write(`GfG, #${i}!`);
}

// Emitting finish event
writable.on('finish', () => {
  console.log('All writes are now complete.');
});

// Calling end function
writable.end('This is the end\n');

// Calling writable.writableFinished  
// Property
writable.writableFinished;
writable.destroy();
```

**输出:**

```
GfG, #0!
GfG, #1!
GfG, #2!
GfG, #3!
GfG, #4!
This is the end

All writes are now complete.

```

**例 2:**

```
// Node.js program to demonstrate the     
// writable.writableFinished Property

// Accessing stream module
const stream = require('stream');

// Creating a stream and creating 
// a write function
const writable = new stream.Writable({

  // Write function with its 
  // parameters
  write: function(chunk, encoding, next) {

    // Converting the chunk of
    // data to string
    console.log(chunk.toString());
    next();
  }
});

// Calling write() method
writable.write('GfG');

// Calling writable.writableFinished  
// Property
writable.writableFinished;
writable.destroy();
```

**输出**

```
GfG
```

在上面的例子中，输出为假，因为在*可写.可写已完成*属性之前没有调用“完成”事件。

**参考:**T2。