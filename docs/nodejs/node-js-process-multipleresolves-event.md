# Node.js 进程多重解析事件

> 原文:[https://www . geesforgeks . org/node-js-process-multipleresolves-event/](https://www.geeksforgeeks.org/node-js-process-multipleresolves-event/)

“多重解析”是流程模块中的一个流程类事件，每当一个承诺被:

*   解决了不止一次。
*   被拒绝了不止一次。
*   解决后被拒绝。
*   拒绝后解决。

**语法:**

```
Event: 'multipleResolves'
```

**参数:**此事件不接受任何参数作为参数。

**返回值**:该事件只返回一个回调函数，用于进一步操作。

**例 1:**

## index.js

```
// Node.js program to demonstrate the  
// Process 'multipleResolves' Event

// Importing process module
const process = require('process');

// Independent Block which will execute
setTimeout(() => {
   console.log('\n')
   console.log('Greetings from GeeksforGeeks');
}, 1000);

// Event 'multipleResolves' 
process.on('multipleResolves', (type, promise, reason) => {

   // Displaying the error 
   console.log("Type: ", type);
   console.log("Promsie: ", promise);
   console.log("Reason: ", reason);
});

const myFunction = async () => {
   const data = await new Promise((resolve, reject) => {

      // Calling reject after multiple resolve
      resolve('Resolve Call One');
      resolve('Resolve Call Two');
      resolve('Resolve Call Three');
      reject(new Error('Reject Error Called'));
   });
   return data
}

// Calling our function
myFunction().then();
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

> 类型:解决
> Promsie:承诺{ '解决呼叫一' }
> 原因:解决呼叫二
> 类型:解决
> Promsie:承诺{ '解决呼叫一' }
> 原因:解决呼叫三
> 类型:拒绝
> Promsie:承诺{ '解决呼叫一' }
> 原因:错误:拒绝数据(C:\ Users \ Lenovo \ Downloads \ geeks \ Node JS \ index . JS:27:14)
> <匿名>(C:\ Users \ Lenovo \ Downloads \ geesforgeks \ Node JS \ index . JS:33:1)
> at Module。_ 编译(内部/模块/cjs/loader . js:1138:30)
> at object . module . _ extensions..js(internal/modules/cjs/loader . js:1158:10)
> at module . load(internal/modules/cjs/loader . js:986:32)
> at function . module . _ load(internal/modules/cjs/loader . js:879:14)
> at function . executeuserentrypoint[as runMain](internal/modules/run _ main . js:71:12)
> at internal/main/main/
> 
> 极客们的问候

**例 2:**

## index.js

```
// Node.js program to demonstrate the  
// Process 'multipleResolves' Event

// Importing process module
const process = require('process');

// Event 'multipleResolves' 
process.on('multipleResolves', (type, promise, reason) => {

   // Displaying the error 
   console.log("Type: ", type);
   console.log("Promsie: ", promise);
   console.log("Reason: ", reason);
});

const myFunction = async () => {
   const data = await new Promise((resolve, reject) => {

      // Calling reject after resolve
      resolve('Single Resolve call');
      reject(new Error('Custom Reason'));
   });
   return data
}

// Calling our function
myFunction().then();
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

> 类型:拒绝
> Promsie: Promise { '单一解析调用}
> 原因:错误:自定义原因
> at data(C:\ Users \ Lenovo \ Downloads \ geesforgeks \ Node JS \ index . JS:19:14)
> at new Promise(<anonymous>)
> at my function(C:\ Users \ Lenovo \ Downloads \ geesforgeks \ Node JS \ index . JS:16:23)
> at Object。<匿名>(C:\ Users \ Lenovo \ Downloads \ geesforgeks \ Node JS \ index . JS:25:1)
> at Module。_ 编译(内部/模块/cjs/loader . js:1138:30)
> at object . module . _ extensions..js(internal/modules/cjs/loader . js:1158:10)
> at module . load(internal/modules/cjs/loader . js:986:32)
> at function . module . _ load(internal/modules/cjs/loader . js:879:14)
> at function . executeuserentrypoint[as runMain](internal/modules/run _ main . js:71:12)
> at internal/main/main

**参考:**[https://nodejs . org/dist/latest-v 16 . x/docs/API/process . html # process _ event _ multipleresolves](https://nodejs.org/dist/latest-v16.x/docs/api/process.html#process_event_multipleresolves)