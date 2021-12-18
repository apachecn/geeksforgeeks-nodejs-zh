# node . js script . createcacheddata()方法

> 原文:[https://www . geesforgeks . org/node-js-script-create cacheddata-method/](https://www.geeksforgeeks.org/node-js-script-createcacheddata-method/)

**script.createCachedData()方法**是一个内置的脚本模块应用编程接口，用于创建一个可以与脚本构造器的 *cachedData* 选项一起使用的代码缓存。它可以在任何时间和任何次数被调用。
**语法:**

```js
script.createCachedData()
```

**参数:**此方法不接受任何参数。
**返回值:**返回缓冲。
以下示例说明了 **script.createCachedData()方法**在 Node.js:
**示例 1:**
中的使用

## java 描述语言

```js
// Node.js program to demonstrate the     
// script.createCachedData() method

// Including vm module
const vm = require("vm");

// Constructing script and defining a
// function add inside it
const script = new vm.Script(`

function add(a, b) {
  return a + b;
}

const x = add(1, 2);
`);

// Calling createCachedData without caching
// the variable x used above
const cacheWithoutx = script.createCachedData();
console.log(cacheWithoutx);
```

**输出:**

```js
<Buffer b5 03 de c0 8a f4 d4 f4 3f 00 00 00
ff 03 00 00 d5 a2 f5 b7 06 00 00 00 00 00 00 
00 28 02 00 00 af 79 f4 0d a0 8c bf b8 00 00
00 80 20 0000 80 00 03 ... >
```

**例 2:**

## java 描述语言

```js
// Node.js program to demonstrate the     
// script.createCachedData() method

// Including vm module
const vm = require("vm");

// Constructing script and defining a
// function add inside it
const script = new vm.Script(`

function add(a, b) {
  return a + b;
}

const x = add(1, 2);
`);

// Calling runInThisContext method
script.runInThisContext();

// Calling createCachedData with caching
// the variable x used above
const cacheWithx = script.createCachedData();
console.log(cacheWithx);
```

**输出:**

```js
<Buffer b5 03 de c0 8a f4 d4 f4 3f 00
00 00 ff 03 00 00 d5 a2 f5 b7 06 00 00 00 00
00 00 00 00 03 00 00 03 67 df 75 6d 4c 36 07
00 00 00 80 20 0000 80 38 04 ... >
```

**参考:**[https://nodejs . org/API/VM . html # VM _ script _ create acheddata](https://nodejs.org/api/vm.html#vm_script_createcacheddata)