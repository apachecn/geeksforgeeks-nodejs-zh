# 如何检查 node.js 中给定的路径是文件还是目录？

> 原文:[https://www . geesforgeks . org/如何检查给定路径是节点中的文件还是目录-js/](https://www.geeksforgeeks.org/how-to-check-the-given-path-is-file-or-directory-in-node-js/)

有时需要检查给定的路径是文件还是目录，以便根据结果执行不同的操作。例如，分别记录目录和文件的信息。
在 Node.js 中，文件处理由 fs 模块处理。你可以在这里了解更多。我们可以用同步和异步的方式检查 Node.js 中文件或目录的路径。

**注意:**如果关心应用性能，异步版本通常更好。

**同步方法:**同步操作非常适合在返回模块之前执行一次性文件/目录操作。要在 fs 模块中检查同步模式下的路径，我们可以使用 statSync()方法。fs.statSync(路径)方法返回 fs 的实例。分配给变量统计的统计。一个 fs。Stats 对象提供关于文件的信息。如果文件路径是文件，stats.isFile()方法返回 true，否则返回 false。如果文件路径是目录，stats.isDirectory()方法返回真，否则返回假。

**例 1:**

```js
// Require the given module 
var fs = require('fs');

// Use statSync() method to store the returned
// instance into variable named stats
var stats = fs.statSync("/Users/divyarani/Documents/geekforgeeks/geeks.js");

// Use isFile() method to log the result to screen
console.log('is file ? ' + stats.isFile());

var stats = fs.statSync("/Users/divyarani/Documents/geekforgeeks/geek");

// Use isDirectory() method to log the result to screen
console.log('is directory ? ' + stats.isDirectory());
```

**输出:**

```js
is file ? true
is directory ? true
```

**例 2:**

```js
// Require the given module 
var fs = require('fs');

// Use statSync() method to store the returned
// instance into variable named stats
var stats = fs.statSync("/Users/divyarani/Documents/geekforgeeks/geek");

// Use isFile() method to log the result to the screen
console.log('is file ? ' + stats.isFile());

var stats = fs.statSync("/Users/divyarani/Documents/geekforgeeks/geeks.js");

// Use isDirectory() method to log the result to screen
console.log('is directory ? ' + stats.isDirectory());
```

**输出:**

```js
is file ? false
is directory ? false
```

**异步方法:**在异步版本中，函数内的代码块对最终用户来说大多是非阻塞的，不会阻止用户对各个子进程执行不同的动作。要在 fs 模块中以异步模式检查路径，我们可以使用 fs.stat()方法。fs.stat()方法有两个参数，第一个参数是路径，第二个参数是回调函数，有两个参数，一个是发生错误时的错误，第二个参数是调用 fs.stat()方法检索的数据，存储在 stats 变量中。如果文件路径是文件，stats.isFile()方法返回 true，否则返回 false。如果文件路径是目录，stats.isDirectory()方法返回真，否则返回假。

**例 1:**

```js
// Require the given module 
var fs = require('fs'),
path = "/Users/divyarani/Documents/geekforgeeks/geek"

// Use stat() method
fs.stat(path, (err, stats) => {
    if( !err ){
         if(stats.isFile()){
             console.log('is file ? ' + stats.isFile());
         }

         else if(stats.isDirectory()){
             console.log('is directory? ' + stats.isDirectory());
         }
     }
     else
         throw err; 
});
```

**输出:**

```js
is directory? true
```

**例 2:**

```js
// Require the given module
var fs = require('fs'),
path = "/Users/divyarani/Documents/geekforgeeks/geeks.js"

// Use stat() method
fs.stat(path, (err, stats) => {
  if( !err ){
       if(stats.isFile()){
           console.log('is file ? ' + stats.isFile());
       }

       else if(stats.isDirectory()){
           console.log('is directory? ' + stats.isDirectory());
       }
   }
   else
      throw err; 
});
```

**输出:**

```js
is file ? true
```