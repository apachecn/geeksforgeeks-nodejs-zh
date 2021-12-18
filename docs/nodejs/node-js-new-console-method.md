# Node.js 新控制台()方法

> 原文:[https://www.geeksforgeeks.org/node-js-new-console-method/](https://www.geeksforgeeks.org/node-js-new-console-method/)

控制台模块提供了一个简单的调试控制台，由 web 浏览器提供，它导出两个特定的组件:

*   一个控制台类，可用于写入任何 Node.js 流。例如: *console.log()* 、 *console.error()、*等。
*   无需导入*控制台*即可使用的全局控制台。例如: *process.stdout、process.stderr、*等。

**新 console()** (在 v8.0.0 中添加)方法是一个内置的“Console”模块的应用程序编程接口，它创建了一个具有单个或多个可写流实例的新 Console，其中 *stdout* 是可写流， *stderr* 用于*警告*或*错误*输出。如果没有提供*标准错误*，则*标准错误*使用标准输出。它是一个控制台，其输出被发送到*进程。stdout* 和*进程。stderr* 。

**注意:**全局控制台方法既不是一致同步的，也不是一致异步的。

**语法:**

```js
new Console(options);
```

**论据:**

```js
const options = { 
   stdout: writableStream, 
   stderr: writableStream, 
   ignoreErrors: true, 
   colorMode:true 
};
```

为了使用这个方法，我们需要使用( *new Console()* )方法创建一个控制台，我们需要导入“*控制台*”和“ *fs* ”模块。

```js
const console = require('console');
const fs = require('fs');  
```

**参数:**该功能接受如上所述和如下所述的对象/参数列表:

**选项** < *对象* > **:** 它在*选项*对象中可能有以下元素。

*   **stdout** < *小溪。可写* > **:接受从 fs 模块导入的写流。**
*   **stderr** < *小溪。可写* > **:也接受从 fs 模块导入的写流。**
*   **忽略错误** < *布尔* > **:传递的默认值为*真*。它会忽略写入底层流时的错误。**
*   **color mode**<*boolean*>|<*string*>**:**传递的默认值为“ *auto* ”。它用于设置仅支持此控制台实例的颜色。根据设置的颜色模式，它可以设置为真、假或“自动”。
*   **检查选项** < *对象* > **:** 它指定传递给[*util . inspect()*](https://www.geeksforgeeks.org/node-js-util-inspect-method/)*方法的选项。*
*   ***组缩进** < *号* > **:** 默认值设置为 2。用于设置组缩进。*

***返回值:**其输出通过 *<流发送到由 fs 模块创建的 *process.stdout* 和 *process.stderr* 文件。可写>* 。*

*下面的例子说明了在 Node.js 中使用*新的控制台(选项)*方法*

***示例 1:** **文件名:index.js***

## *java 描述语言*

```js
*// Node.js program to demonstrate the
// new Console() method

// Using require to access fs module
const fs = require('fs');

// Using require to access console module
const { Console } = require('console');

// Creating write Stream
const output = fs.createWriteStream('./out.log');
const errorOutput = fs.createWriteStream('./err.log');

//
const options = { stdout: output, stderr: errorOutput,
ignoreErrors: true, colorMode: false };
const logger = new Console(options);

const count = 5;

// Using like console
logger.log('count: %d', count);
console.log("Successfully created and logged via console...", )*
```

*使用以下命令运行 **index.js** 文件:*

```js
*node index.js*
```

***输出:***

> ***注意:**上面的 node.js 示例将在 **index.js** 文件所在的同一个文件夹中创建日志文件(out & err)。*
> 
> *>>通过控制台成功创建和记录…*

***示例 2:** **文件名:index.js***

## *java 描述语言*

```js
*// Node.js program to demonstrate the
// new Console() method

// Using require to access fs module
const fs = require('fs');

// Using require to access console module
const console = require('console');
const { Console } = console;

try {
 // Creating write Stream
 const output = fs.createWriteStream('./outputlog.txt');
 const error = fs.createWriteStream('./errlog.txt');

 // Creating new Console
 const objLogger   = new Console(
    { stdout: output, stderr: error,
     ignoreErrors: true, colorMode: true }
);

 // Custom write Stream
 const outt = fs.createWriteStream('./output.log');
 const err = fs.createWriteStream('./error.log');

 // Another way to create console
 // (default values are passed to options)
 const logObject = new console.Console(outt, err);

 // Creating family object
 var family = {};
 family.Head = 'Miss Sanno';
 family.headDesignation = 'Teacher';
 family.Member1 = 'Miss Sanchi';
 family.member1Designation = 'Kid';
 family.Member2 = 'Master Amit';
 family.member2Designation = 'Student';

 // Creating constant value count
 const count = 25+75*5-5/2;
 // Writing via console
 objLogger.log('Family: %s', family);
 // Printing Family Object to console
 console.log('Family Stream Created: ', family);
 // Writing via console
 logObject.log('Count: %s', count);
 // Printing count to console
 console.log('Count Stream Created: ', count);
 // console.log(logObject.family.error)
 }
catch {
  console.error(new Error(
    'Oops, some error happened in family...'));
  // Prints: [Error: Oops, some error
  // happened in family...], to stderr
}*
```

*使用以下命令运行 **index.js** 文件:*

```js
*node index.js*
```

***输出:***

> ***注意:**上面的 node.js 示例将在 index.js 文件所在的同一个文件夹中创建日志文件(输出&错误)。
> 家庭流创建:{
> 头:【桑诺小姐】，
> 头指定:【老师】，
> 成员 1:【桑奇小姐】，
> 成员 1 指定:【小鬼】，
> 成员 2:【阿米特大师】，
> 成员 2 指定:【学生】
> }
> 计数流创建:397.5*

***参考:**[https://nodejs . org/API/console . html # console _ new _ console _ options](https://nodejs.org/api/console.html#console_new_console_options)*