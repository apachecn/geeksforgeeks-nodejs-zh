# node . js 和浏览器之间如何共享代码？

> 原文:[https://www . geesforgeks . org/如何在节点 js 和浏览器之间共享代码/](https://www.geeksforgeeks.org/how-to-share-code-between-node-js-and-the-browser/)

在本文中，我们将探讨如何编写客户端和服务器端应用程序都可以使用的 JavaScript 模块。
我们有一个小的 web 应用程序，它有一个 JavaScript 客户端(在浏览器中运行)和一个与之通信的 Node.js 服务器。我们有一个函数 getFrequency()，服务器和客户端都可以使用它来获取给定字符串中字符的频率。我们希望创建一套方法，以便在两端完成任务。
**方法:**
为客户端(在浏览器中运行)编写代码与服务器端 Node.js 应用程序有很大不同。在客户端，我们主要处理 DOM 或者像 cookies 这样的 web APIs，但是这些东西在 Node 中是不存在的。我们不能在客户端使用节点模块的其他原因是节点使用 **CommonJS** 模块系统，而浏览器使用标准 **ES Modules** ，语法不同。
在节点中，我们使用 module.exports 来公开功能或属性。但是，这将在浏览器中中断，因为浏览器无法识别**导出**。因此，为了使它工作，我们检查**是否导出了**，如果没有，那么我们为导出函数创建一个合理的对象。在浏览器中，这可以通过创建一个与模块同名的全局变量来实现。
模块的结构如下所示:
**sample module . js**

## java 描述语言

```
// Checking if exports is defined
if(typeof exports === 'undefined'){
   var exports = this['sampleModule'] = {};
}

// The code define the functions,
// variables or object to expose as
// exports.variableName
// exports.functionName
// exports.ObjectName

// Function not to expose
function notToExport(){ }

// Function to be exposed
exports.test(){ }
```

上面的格式有一个问题，我们在 **sampleModule.js** 中定义但未导出的任何内容都将对浏览器可用，即函数 notToExport()和 test()都将在该文件之外工作。因此，为了克服这一点，我们用一个闭包来包装这个模块。
T3T5】

## java 描述语言

```
(function(exports) {

   // The code defines all the functions,
   // variables or object to expose as:
   // exports.variableName
   // exports.functionName
   // exports.ObjectName

}) (typeof exports === 'undefined'? this['sampleModule']={}: exports);
```