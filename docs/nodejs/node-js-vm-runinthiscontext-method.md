# node . js VM . runintiscontext()方法

> 原文:[https://www . geesforgeks . org/node-js-VM-runintiscontext-method/](https://www.geeksforgeeks.org/node-js-vm-runinthiscontext-method/)

方法编译代码，在当前全局的上下文中运行，然后返回输出。此外，运行的代码不能访问本地范围，但可以访问当前的全局对象。

**语法:**

```js
vm.runInThisContext( code, options )
```

**参数:**该方法接受两个参数，如 avobe 所述，描述如下:

*   **Code:** is JavaScript code to be compiled and run.
*   **option:** is an optional parameter, which returns *object* or *string* ; if it is a string, it defines the file name of the returned string.

**返回值:**返回脚本中最后一条语句的执行结果。

下面的例子说明了在 Node.js 中使用**VM . runintiscontext()方法**:

**例 1:**

```js
// Node.js program to demonstrate the     
// runInThisContext() method

// Including vm module
const vm = require('vm');

// Declaring local variable
let localVar = 'GfG';

// Calling runInThisContext method
const vmresult =
 vm.runInThisContext('localVar = "Geeks";');

// Prints output for vmresult
console.log(`vmresult: '${vmresult}', 
              localVar: '${localVar}'`);

// Constructing eval
const evalresult = eval('localVar = "CS";');

// Prints output for evalresult
console.log(`evalresult: '${evalresult}', 
                localVar: '${localVar}'`);
```

**输出:**因此，vm.runInThisContext()方法不能访问本地范围。因此，localVar 在这里保持不变。

```js
vmresult: 'Geeks', 
                   localVar: 'GfG'
evalresult: 'CS', 
                localVar: 'GfG'
```

**例 2:**

```js
// Node.js program to demonstrate the     
// runInThisContext() method

// Including vm module
const vm = require('vm');

// Declaring local variable and assigning
// it an integer
let localVar = 6;

// Calling runInThisContext method
const vmresult = 
vm.runInThisContext('localVar = 9;');

// Prints output for vmresult
console.log(`vmresult: '${vmresult}',
             localVar: '${localVar}'`);

// Constructing eval
const evalresult = eval('localVar = 11;');

// Prints output for evalresult
console.log(`evalresult: '${evalresult}',
                localVar: '${localVar}'`);
```

**输出:**

```js
vmresult: '9', 
                  localVar: '6'
evalresult: '11',
                localVar: '6'

```

**参考:**[https://nodejs . org/API/VM . html # VM _ VM _ runinhiscontext _ code _ options](https://nodejs.org/api/vm.html#vm_vm_runinthiscontext_code_options)