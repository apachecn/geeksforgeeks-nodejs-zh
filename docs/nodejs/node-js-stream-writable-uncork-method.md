# Node.js Stream 可写. unlock()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-written-unlock-method/](https://www.geeksforgeeks.org/node-js-stream-writable-uncork-method/)

**可写. unlock()方法**是 Stream 模块的内置应用编程接口，用于在调用 stream.cork()方法时刷新所有缓冲的数据。

**语法:**

```
writable.uncork() 
```

**参数:**此方法不接受任何参数。

**返回值:**如果正在调用这个方法，那么被塞住的数据将再次显示在输出中。

下面的例子说明了在 Node.js 中**可写. Below()方法**的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// writable.uncork() method  
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

// Calling uncork() function
writable.uncork();
```

**输出:**

```
hi
hello
world

```

在上面的例子中，被塞住的数据也在输出中返回，因为在此之后调用了 uncork()函数。

**例 2:**

```
// Node.js program to demonstrate the     
// writable.uncork() method  
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

// Calling cork() function
writable.cork();

// Writing data
writable.write('hi');

// Calling cork() function
writable.cork();

// Again writing some data
writable.write('hello');

// Calling uncork function
// using nextTick()
process.nextTick(() => {

  // Calling uncork function
  writable.uncork();

  writable.uncork();
});
```

**输出:**

```
hi
hello

```

所以，你需要调用 uncork()函数调用科克函数的次数。在上面的例子中，我们已经调用了两次科克()函数，所以 uncork 函数也被调用了两次。

**参考:**T2】https://nodejs.org/api/stream.html#stream_writable_uncork