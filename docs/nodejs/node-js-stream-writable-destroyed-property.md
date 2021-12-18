# 节点. js 流可写.已破坏属性

> 原文:[https://www . geesforgeks . org/node-js-stream-written-destroy-property/](https://www.geeksforgeeks.org/node-js-stream-writable-destroyed-property/)

**可写.销毁属性**是 Stream 模块的内置应用编程接口，用于检查可写.销毁()方法是否被调用。

**语法:**

```js
writable.destroyed
```

**返回值:**如果在调用 destroy()方法之前调用了该方法，则该属性返回 true，否则返回 false。

下面的例子说明了在 Node.js 中**可写的.销毁属性**的使用:

**例 1:**

```js
// Node.js program to demonstrate the     
// writable.distroyed Property

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

// Writing data
writable.write('hi');

// Again writing some data
writable.write('hello');

// Calling destroy function
writable.destroy();

// Calling the Property
writable.destroyed;
```

**输出:**

```js
hi
hello
true

```

**例 2:**

```js
// Node.js program to demonstrate the     
// writable.distroyed Property

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

// Writing data
writable.write('hi');

// Again writing some data
writable.write('hello');

// Calling the Property
writable.destroyed;
```

**输出:**

```js
hi
hello
false

```

在上面的示例中，输出为 false，因为在调用属性 writable.destroy 之前没有调用*可写. destroy()* 方法。

**参考:**[https://nodejs . org/API/stream . html # stream _ written _ destroled](https://nodejs.org/api/stream.html#stream_writable_destroyed)