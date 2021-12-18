# node . js | script . runintiscontext()方法

> 原文:[https://www . geesforgeks . org/node-js-script-runinhiscontext-method/](https://www.geeksforgeeks.org/node-js-script-runinthiscontext-method/)

方法运行虚拟机内部的编译代码。当前全局对象上下文中的脚本。此外，运行代码不能访问本地范围，但可以访问当前的全局对象。

**语法:**

```js
script.runInThisContext( options )
```

**参数:**该方法接受单参数**选项**，可选，返回*对象*。选项有*显示错误*、*超时*和*中断起始*。

**返回值:**返回脚本中最后一条语句的执行结果。

下面的例子说明了在 Node.js 中使用**script . runintiscontext()方法**:

**例 1:**

```js
// Node.js program to demonstrate the     
// script.runInThisContext() method

// Including vm module
const vm = require('vm');

// Defining code
let code = 'console.log("I am an author?");';

// Defining script
let script = new vm.Script(code);

// Calling runInThisContext method
script.runInThisContext();
```

**输出:**

```js
I am an author?
```

**例 2:**

```js
// Node.js program to demonstrate the     
// script.runInThisContext() method

// Including vm module
const vm = require('vm');

// Defining x and y
 var x = 40; var y = 17;

// Adding x and y
const z = x + y;

// Dwfining code
let code = console.log(z);

// Defining script
let script = new vm.Script(code);

// Calling runInThisContext method
script.runInThisContext();
```

**输出:**

```js
57
```

**参考:**[https://nodejs . org/API/VM . html # VM _ script _ runinhiscontext _ options](https://nodejs.org/api/vm.html#vm_script_runinthiscontext_options)