# node . js process . HR time . bigint()方法

> 原文:[https://www . geesforgeks . org/node-js-process-HR time-big int-method/](https://www.geeksforgeeks.org/node-js-process-hrtime-bigint-method/)

**process.hrtime.bigint()** 方法返回当前高分辨率实时(以纳秒为单位)作为 NodeJS 中的 **bigint** 。它不支持额外的时间参数，因为可以通过减去两个**大整数**变量来直接计算差值。

我们用它减去开始时间和结束时间来计算过程之间的总时间，单位为纳秒。

**语法:**

```js
process.hrtime.bigint();
```

**参数:**该函数不取任何参数。

**返回类型:**返回 *bigint。*

**示例 1:** 使用以下代码创建一个 *index.js* 文件。

## index . js

```js
// Create a variable and call the 
// process.hrtime() function
var start_time = process.hrtime.bigint();

// Print the Start time
console.log("Start Time:", start_time);

// Make the add function 
setTimeout(function () {

    console.log("Execution time will be calculated....");

    // Create a variable and call the second 
    // process.hrtime() function
    var end_time = process.hrtime.bigint();

    // Print the Execution time
    console.log("End Time:", end_time - start_time);

}, 2000);
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Start Time: 507990695929600n
Execution time will be calculated....
End Time: 1005191900n
```

**示例 2:** 使用以下代码创建一个 *index.js* 文件。

**索引. js**

## 【JavaScript】

```js
// Create a variable and call the 
// process.hrtime() function
var start_time = process.hrtime.bigint();

// Print the Start time
console.log("Start Time:", start_time);

// Make the add function 
setTimeout(function () {

    // Create two variable
    var a = '45',
        b = '40';

    // Print the Subtraction result
    console.log("Subtraction of two number is :", 
            (a - 0) - (b - 0));

    // Create a variable and call the  
    // second process.hrtime() function
    var end_time = process.hrtime.bigint();

    // Print the Execution time
    console.log("End Time:", end_time - start_time);

}, 1000);
```

**输出:**

```js
Start Time: 507818309465700n
Subtraction of two number is : 5
End Time: 1008706600n
```

**参考:**[https://nodejs . org/API/process . html # process _ process _ HR time _ bigint](https://nodejs.org/api/process.html#process_process_hrtime_bigint)