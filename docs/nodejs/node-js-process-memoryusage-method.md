# Node.js process.memoryUsage()方法

> 原文:[https://www . geesforgeks . org/node-js-process-memoryusage-method/](https://www.geeksforgeeks.org/node-js-process-memoryusage-method/)

**process.memoryUsage()** 方法是流程模块的一种内置方法，它提供关于 Node.js 程序的当前流程或运行时的信息。内存使用方法返回一个对象，描述 Node.js 进程的内存使用情况(以字节为单位)。

**语法:**

```js
process.memoryUsage()   
```

**参数:**此方法不接受任何参数:

**返回值:**这个方法返回一个对象，描述内存使用情况。

下面的例子说明了 **process.memoryUsage()** 方法在 Node.js 中的使用

**例 1:**

## index . js

```js
// Requiring module
var process = require('process')

// Prints the output as an object
console.log(process.memoryUsage())
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
{
  rss: 23851008,     
  heapTotal: 4907008,
  heapUsed: 2905912, 
  external: 951886,  
  arrayBuffers: 17574
}
```

**例 2:**

## index . js

```js
// Requiring module
var process = require('process')

// An example displaying the respective memory
// usages in megabytes(MB)
for (const [key,value] of Object.entries(process.memoryUsage())){
    console.log(`Memory usage by ${key}, ${value/1000000}MB `)
}
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Memory usage by rss, 23.87968MB 
Memory usage by heapTotal, 4.907008MB
Memory usage by heapUsed, 2.907088MB
Memory usage by external, 0.951886MB
Memory usage by arrayBuffers, 0.017574MB
```

**参考:**[https://nodejs . org/API/process . html # process _ process _ memory usage](https://nodejs.org/api/process.html#process_process_memoryusage)