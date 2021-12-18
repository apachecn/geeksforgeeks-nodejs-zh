# 如何处理 node.js 中的错误？

> 原文:[https://www . geesforgeks . org/如何处理节点中的错误-js/](https://www.geeksforgeeks.org/how-to-handle-errors-in-node-js/)

Node.js 是一个用于服务器端脚本的 JavaScript 扩展。错误处理是应用程序开发中的一个强制性步骤。Node.js 开发人员可以同时使用同步和异步函数。处理异步函数中的错误很重要，因为它们的行为可能不同于同步函数。虽然 try-catch 块对同步函数有效，但异步函数可以处理回调、承诺和异步等待。Try-catch 是同步的，这意味着如果异步函数在同步 try/catch 块中引发错误，则不会引发错误。Node.js 应用程序中引发的错误可以通过以下方式处理:

1.  使用试捕块
2.  使用回调
3.  使用承诺和承诺回调
4.  使用异步等待

**使用 try-catch 块:**try-catch 块可用于处理代码块引发的错误。

```
function dosomething(){
    throw new Error(
    'a error is thrown from dosomething');
}

function init(){
    try{
        dosomething();
    }
    catch(e){
        console.log(e);
    }
 console.log(
    "After successful error handling");
}

init();
```

**输出:**

```
Error: a error is thrown from dosomething
    at dosomething (/home/cg/root/6422736/main.js:4:11)
    at init (/home/cg/root/6422736/main.js:9:9)
    at Object. (/home/cg/root/6422736/main.js:17:1)
    at Module._compile (module.js:570:32)
    at Object.Module._extensions..js (module.js:579:10)
    at Module.load (module.js:487:32)
    at tryModuleLoad (module.js:446:12)
    at Function.Module._load (module.js:438:3)
    at Module.runMain (module.js:604:10)
    at run (bootstrap_node.js:389:7)
After successful error handling

```

**解释:**调用 init()函数，该函数又调用 dosomething()函数，该函数抛出一个错误对象。init()方法的 catch 块捕获了此错误对象。如果没有正确处理错误，程序将终止。catch 块打印调用堆栈以显示错误发生的点。

**使用回调:**回调是在某个任务完成时调用的函数。回调在 Node.js 中被广泛使用，因为它可以防止任何阻塞，并允许同时运行其他代码。程序不等待文件读取完成，并在继续读取文件的同时继续打印“程序结束”。如果出现任何错误，如系统中不存在文件，则在“程序结束”后打印错误，否则输出文件内容。

```
var fs = require("fs");

fs.readFile('foo.txt', function (err, data) {
   if (err) {
       console.error(err);
}else{
   console.log(data.toString());
}
});

console.log("Program Ended");
```

**输出:**

```
Program Ended
[Error: ENOENT: no such file or directory, 
  open 'C:\Users\User\Desktop\foo.txt'] {
  errno: -4058,
  code: 'ENOENT',
  syscall: 'open',
  path: 'C:\\Users\\User\\Desktop\\foo.txt'
}

```

**解释:**在这种情况下，文件不存在于系统中，因此抛出错误。

**使用承诺和承诺回调:**承诺是 Node.js 回调的增强。定义回调时，返回的值称为“承诺”。承诺和回调的关键区别在于返回值。回调中没有返回值的概念。返回值为定义回调函数提供了更多的控制。为了使用 promise，必须在应用程序中安装和导入 promise 模块。那个。然后子句处理承诺的输出。如果出现任何错误。然后条款或如果任何上述承诺被拒绝，它被传递给直系亲属。捕获条款。如果承诺被拒绝，并且没有错误处理程序，那么程序终止。

```
var Promise = require('promise');
var MongoClient = require('mongodb').MongoClient;
var url = 'mongodb://localhost/TestDB';

MongoClient.connect(url)
    .then(function(err, db) {
        db.collection('Test').updateOne({
            "Name": "Joe"
        }, {
            $set: {
                "Name": "Beck"
            }
        });
    });
   .catch(error => alert(error.message)) 
```

**输出:**

```
// In this case we assume the url is wrong
MongoError: failed to connect to server [localhost:27017]
// error message may vary

```

**使用异步等待:**异步等待是一种特殊的语法，以一种简单易懂的方式处理承诺。当我们使用异步/等待时。然后被处理函数中等待的 await 替换。错误处理由。捕获条款。async-wait 也可以封装在 try-catch 块中，用于错误处理。如果不存在错误处理程序，程序将因未捕获的错误而终止。

```
async function f() {
  let response = await fetch('http://xyzurl');
}

// f() becomes a rejected promise
f().catch(alert);
```

**输出:**

```
// the url is wrong //
TypeError: failed to fetch 

```