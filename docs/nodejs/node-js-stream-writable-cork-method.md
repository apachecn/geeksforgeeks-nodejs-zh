# Node.js Stream 可写. cock()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-written-cork-method/](https://www.geeksforgeeks.org/node-js-stream-writable-cork-method/)

**可写.科克()方法**是 Stream 模块的内置应用编程接口，用于将每个数据写入缓冲存储器。当我们使用 stream.uncork()或 stream.end()方法时，缓冲区数据将被刷新。

**语法:**

```js
writable.cork() 
```

**参数:**此方法不接受任何参数。

**返回值:**如果使用此方法，则在此方法之后写入的数据不会显示在输出中，因为这些数据存储在内存中，并且可以使用一些其他特定方法再次显示。

以下示例说明了 Node.js 中**可写.科克()方法**的使用:

**例 1:**

```js
// Node.js program to demonstrate the     
// writable.cork() method  
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

// Calling cork() function
writable.cork();

// Again writing some data
writable.write('hello');
writable.write('world');
```

**输出:**

```js
hi
true
```

这里，在上面的例子中，仅显示在*软木()*方法之前写入的数据，并且在其被软木化之后写入的数据，即存储在存储器中。

**例 2:**

```js
// Node.js program to demonstrate the     
// writable.cork() method  
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
writable.write('world');

// Calling cork() function
writable.cork();
```

**输出**

```js
hi
hello
world

```

在上面的例子中，科克()方法最终被写入，因此，没有任何数据被存储在内存中。因此，所有写入的数据都会显示在输出中。

**参考:**T2】https://nodejs.org/api/stream.html#stream_writable_cork