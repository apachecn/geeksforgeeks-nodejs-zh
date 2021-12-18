# Node.js console.profile()方法

> 原文:[https://www . geesforgeks . org/node-js-console-profile-method/](https://www.geeksforgeeks.org/node-js-console-profile-method/)

控制台模块提供了一个简单的调试控制台，由 web 浏览器提供，它导出两个特定的组件:

*   一个控制台类，可用于写入任何 Node.js 流。示例: *console.log()、console.error()* 等。
*   无需导入控制台即可使用的全局控制台。例如: *process.stdout，process.stderr* 等。

***console . profile()***(*在 v8.0.0* 中添加)方法是“ *console* 模块的内置应用编程接口，除非在检查器中使用，否则不会显示任何内容。它开始一个带有可选标签的 JavaScript CPU 配置文件，直到调用 *console.profile()* 为止。该配置文件随后被添加到检查器的“配置文件”面板中。

**注意:**全局控制台方法既不是一致同步的，也不是一致异步的。

**语法:**

```js
console.profile([label])

```

**参数:**该函数接受如上所述的单个参数，如下所述:

*   **标签** < *字符串* > **:** 它接受进一步在检查器中使用的标签名称。

**返回值:**它不在控制台打印任何东西，而是在检查器中启动一个 JavaScript CPU 配置文件。

以下示例说明了在 Node.js 中使用 *console.profile()* 方法

**示例 1:文件名:index.js**

```js
// Node.js program to demonstrate the 
// console.profile() Method

// Starting MyLabel console profile
console.profile('MyLabel');

// Doing some task
for (var i = 0; i < 4; i++) {

  // Printing some task
  console.log('Doing task no:', i);
}

// Finishing MyLabel profile
console.profileEnd('MyLabel');
```

使用以下命令运行 **index.js** 文件:

```js
node index.js

```

**控制台输出:**

```js
Doing task no: 0
Doing task no: 1
Doing task no: 2
Doing task no: 3

```

**检验员输出:**

![](img/f3df7ee5cb2f694673841566424393a0.png)

检查器中的输出

**示例 2:文件名:index.js**

```js
// Node.js program to demonstrate the 
// console.profile() Method

// New profile function
function newProfile(callback) {      
  try {
      // Doing some task
      for(var i = 1; i < 4; i++) {
         console.log('Working on task:', i);
         callback();      
      }
    } catch {

      // Prints if there is error
      console.error('error occured');
    }
}

// Starting newProfile() console profile
console.profile("newProfile()");

// Calling newprofile()
newProfile(function alfa() {

  // Finishing profile
  console.profileEnd();
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js

```

**控制台输出:**

```js
Working on task: 1
Working on task: 2
Working on task: 3

```

**检验员输出:**

![](img/29a5ace9d4646bd0e816fe38900d2227.png)

检查器中的输出

**参考:**[https://nodejs . org/API/console . html # console _ console _ profile _ label](https://nodejs.org/api/console.html#console_console_profile_label)