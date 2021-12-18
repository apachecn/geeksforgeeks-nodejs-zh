# 使用导出从 Node.js 文件公开功能

> 原文:[https://www . geesforgeks . org/expose-functional-from-a-node-js-file-use-exports/](https://www.geeksforgeeks.org/expose-functionality-from-a-node-js-file-using-exports/)

**模块.导出应用编程接口将数据暴露给其他文件**

节点支持内置模块系统。Node.js 可以导入由其他 Node.js 文件公开的功能。要导入某些内容，您需要使用当前文件夹中存在的 **library.js** 文件公开的导入功能。

```
const library = require('./library')                // Path
```

必须先公开文件中的功能，然后才能将其导入任何其他文件。默认情况下，文件中定义的对象是私有的，不对外公开。

*模块.导出*文件 API 由*模块*系统提供，在代码中实现。
*模块*是表示当前模块的变量，*导出*是将作为模块暴露的对象。因此，模块、导出和导出都将作为模块公开。

*module.exports* 基本上是一个返回*请求*调用结果的对象。

您需要新的*导出*属性来导入应用程序任何其他部分中的对象或函数。您可以通过两种方式做到这一点:

第一种方法是将对象分配给*模块。导出*，其中对象由模块系统开箱提供。

**示例:**

```
const person = {
    firstName: 'John',
    lastName: 'Smith'
}

module.exports = Person

// in the file where you want to export

const person= require(‘./person)
```

第二种方法是将导出的对象添加为导出的属性。您可以使用导出来导出多个对象、函数或数据:

```
const Person = {
    firstName: 'John',
    lastName: 'Smith'
}

exports.person = person
```

或者直接

```
exports.person = {
    firstName: 'John',
    lastName: 'Smith'
}
```

您将通过在另一个文件中引用导入的属性来使用它:

```
Const items = require('items')
items.person
```

或者

```
const person= require('./items').person
```

**模块出口和出口有什么区别？**

前者公开它所指向的对象，而后者公开它所指向的对象的属性。