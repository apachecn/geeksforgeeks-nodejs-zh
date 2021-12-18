# Node.js Stream 可写. writable ked 属性

> 原文:[https://www . geesforgeks . org/node-js-stream-writteablecorked-property/](https://www.geeksforgeeks.org/node-js-stream-writable-writablecorked-property/)

**written . writteablecorked 属性**是 stream 模块的内置应用编程接口，用于检查需要调用 unlock()函数的次数，以便可以完全取消对 Stream 的锁定。

**语法:**

```js
writable.writableCorked 
```

**返回值:**返回一个整数值，表示需要调用 write . un core()的次数。

下面的例子说明了在 Node.js 中**可写.可写.可写属性**的使用:

**例 1:**

```js
// Node.js program to demonstrate the     
// writable.writableCorked Property

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

// Calling cork function
writable.cork();

// Writing data
writable.write('hi');

// Again calling cork function
writable.cork();

// Again writing some data
writable.write('GFG');

// Calling writable.writableCorked 
// Property
writable.writableCorked;
```

**输出:**

```js
2

```

**例 2:**

```js
// Node.js program to demonstrate the     
// writable.writableCorked Property

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

// Calling cork function
writable.cork();

// Writing data
writable.write('hi');

// Calling uncork() function
writable.uncork();

// Again calling cork function
writable.cork();

// Again writing some data
writable.write('GFG');

// Calling writable.writableCorked 
// Property
writable.writableCorked;
```

**输出:**

```js
hi
1

```

在上面的例子中，我们已经调用了一次 uncork()函数。因此，为了完全打开流，您只需要调用 unlock()函数一次，因此，输出是一个。

**参考:**[https://nodejs . org/API/stream . html # stream _ writable _ writablecorked](https://nodejs.org/api/stream.html#stream_writable_writablecorked)