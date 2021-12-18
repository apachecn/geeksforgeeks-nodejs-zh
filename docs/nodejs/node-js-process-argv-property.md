# Node.js process.argv 属性

> 原文:[https://www . geesforgeks . org/node-js-process-argv-property/](https://www.geeksforgeeks.org/node-js-process-argv-property/)

**process.argv 属性**是进程模块的内置应用编程接口，用于在命令行中运行时获取传递给 node.js 进程的参数。

**语法:**

```
process.argv
```

**返回值:**该属性返回一个数组，该数组包含在命令行中运行进程时传递给进程的参数。第一个元素是流程执行路径，第二个元素是 js 文件的路径。

下面的例子说明了 **process.argv 属性**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the
// process.argv Property

// Include process module
const process = require('process');

// Printing process.argv property value
console.log(process.argv);
```

**运行代码的命令:**

```
node index.js extra_argument1 extra_argument2 3
```

**输出:**

```
[ 'C:\\Program Files\\nodejs\\node.exe',
  'C:\\nodejs\\g\\process\\argv_1.js',
  'extra_argument1',
  'extra_argument2',
  '3' 
]

```

**例 2:**

```
// Node.js program to demonstrate the
// process.argv Property

// Include process module
const process = require('process');

// Printing process.argv property value
var args = process.argv;

console.log("number of arguments is "+args.length);

args.forEach((val, index) => {
    console.log(`${index}: ${val}`);
});
```

**运行代码的命令:**

```
node index.js extra_argument1 extra_argument2 3
```

**输出:**

```
number of arguments is 5
0: C:\Program Files\nodejs\node.exe
1: C:\nodejs\g\process\argv_2.js
2: extra_argument1
3: extra_argument2
4: 3

```

**注意:**上面的程序将通过使用`node filename.js`命令后跟参数来编译和运行。

**参考:**T2】https://nodejs.org/api/process.html#process_process_argv