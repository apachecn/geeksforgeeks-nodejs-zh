# 模块导出和节点 js 中导出的区别

> 原文:[https://www . geesforgeks . org/模块导出和节点中导出之间的差异-js/](https://www.geeksforgeeks.org/difference-between-module-exports-and-exports-in-node-js/)

**模块**是一个简单的 JavaScript 对象，代表当前模块。它是每个模块的本地，也是私有的。它有**导出**属性，这是一个普通的 JavaScript 变量，设置为**模块。导出。**在文件的末尾，Node.js 返回*模块。导出*到所需的函数。

### **关于模块.出口:**

当我们想要将单个类/变量/函数从一个模块导出到另一个模块时，我们使用 *module.exports* 方式。

**示例:**创建两个文件 *calculator.js* 和 *operation.js* 并使用*模块导出*方法将算术类从 *calculator.js* 导出到 *operation.js* 。这里，我们创建了一个类算术，并使用*模块导出了整个类。*

**文件名:calculator . js**

## Javascript

```js
class Artimatics {
    constructor(a, b) {
        this.a = a;
        this.b = b;
    }

    add() {
        return this.a + this.b;
    }
    subtract() {
        return this.a - this.b;
    }

    multiply() {
        return this.a * this.b;
    }

    divide() {
        if (this.b != 0) {
            return this.a / this.b;
        }
        return "divided by zero !!!!";
    }
};

module.exports = Artimatics;
```