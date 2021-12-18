# Node.js util.inherits()方法

> 原文:[https://www.geeksforgeeks.org/node-js-util-inherits-method/](https://www.geeksforgeeks.org/node-js-util-inherits-method/)

“util”模块提供用于调试目的的“实用”功能。为了访问这些函数，我们需要调用它们(通过“require”(“util”))。

util.inherits()(在 v0.3.0 中添加)方法是 util 模块的内置应用程序编程接口，在该接口中，构造函数将原型方法从一个方法继承到另一个方法，并且该构造函数的原型被设置为从 superConstructor 创建的新对象。它主要用于在*object . set rototypeof(constructor . prototype，superstructor . prototype)*之上添加或继承一些输入验证。为了更加方便，可以通过*constructor . super _ property*进行访问。它的(即 *util.inherits()* )用法不太受鼓励，为了获得语言级继承支持，建议使用 ES6 类和 extends 关键字。

**语法:**

```
const util = require('util');
util.inherits(constructor, superConstructor)

```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **构造函数** *<函数>* **:** 用户希望从类中继承的是任何<函数>。

*   **超结构** *<函数>* **:** 是任意的<函数>，多用于添加或继承一些输入验证。

    **返回值** < *未定义* >:返回未定义值。

    **示例 1:** 文件名:index.js

    ```
    // Node.js program to demonstrate the 
    // util.inherits() method 

    // Using require to access util module 
    const util = require('util'); 
    const emitEvent = require('events');

    // MyStream function calling EventEmitter
    function streamData() {
      emitEvent.call(this);
    }

    // Trying to print value
    console.log("1.> Returning util.inherits():", 
    util.inherits(streamData, emitEvent)); 
    // Returns undefined

    // Inheriting library via constructor
    console.log("2.>", streamData);
    // Whole library of the constructor

    console.log("3.>", emitEvent);
    // Inheriting from EventEmitter 
    util.inherits(streamData, emitEvent);

    // Emiting events
    streamData.prototype.write = function(responseData) {
      this.emit('send_data', responseData);
    };

    // Creating new stream by calling function
    const stream = new streamData('default');
    // Printing instance of eventemitter
    console.log("4.> Instance of EventEmitter", 
                  stream instanceof emitEvent); 
    // Returns true

    // Comparing value and type of an 
    // instance with eventEmitter
    console.log("5.> '===' comparison of an "
              + "Instance with EventEmitter", 
    streamData.super_ === emitEvent); 
    // Returns true

    stream.on('send_data', (responseData) => {
      console.log("6.>", 
      `Data Stream Received: "${responseData}"`);
    });

    // Writing on console
    stream.write('Finally it started!'); 
    // Finally Received the data
    ```

    使用以下命令运行 **index.js** 文件:

    ```
    node index.js
    ```

    **输出:**

    > 1.>返回 util.inherits():未定义
    > 
    > 2.>[功能:流数据]
    > 
    > 3.><ref>【功能:事件发射器】{一次:【功能:一次】，…..，listener count:[函数(匿名)]</ref>
    > 
    > 4.>事件发射器实例为真
    > 
    > 5.> ' === '实例与事件发射器的比较为真
    > 
    > 6.>收到数据流:“终于开始了！”

    **示例 2:** **文件名:index.js**

    ```
    // Node.js program to demonstrate the 
    // util.inherits() method in ES6

    // Using require to access util module 
    const util = require('util');
    const { inspect } = require('util');
    const emitEvent = require('events');

    class streamData extends emitEvent {
      write(stream_data) {

          // Emitting the data stream
        this.emit('stream_data', stream_data);
      }
    }

    const manageStream = new streamData('default');
    console.log("1.>", inspect(manageStream, false, 0, true))
    console.log("2.>", streamData)

    // Returns true
    console.log("3.>", streamData === manageStream) 
    console.log("4.>", manageStream)
    manageStream.on('stream_data', (stream_data) => {
      // Prints the write statement after streaming
      console.log("5.>", `Data Stream Received: "${stream_data}"`);
    });

    // Write on console
    manageStream.write('Finally it started streaming with ES6');
    ```

    使用以下命令运行 **index.js** 文件:

    ```
    node index.js
    ```

    **输出:**

    > 1.>流数据{ _ 事件:[对象:空原型] {}，……………………，[符号(kCapture)]: false}
    > 
    > 2.>[功能:流数据]
    > 
    > 3.>假
    > 
    > 4.> stream data { _ events:[对象:空原型] {}，……………………，[符号(kCapture)]: false}
    > 
    > 5.>接收的数据流:“最后，它开始与 ES6 进行流式传输”

    **参考:**[https://nodejs . org/API/util . html # util _ util _ inherits _ constructor _ super structor](https://nodejs.org/api/util.html#util_util_inherits_constructor_superconstructor)