# Node.js process.hrtime()方法

> 原文:[https://www . geesforgeks . org/node-js-process-HR time-method/](https://www.geeksforgeeks.org/node-js-process-hrtime-method/)

**process.hrtime(** )方法测量代码执行时间，返回包含当前高分辨率实时的数组，单位为[秒，纳秒]。我们通过提供第一个 process.hrtime()调用返回的时间作为第二个 process.hrtime()调用中的参数来度量代码执行时间。

process.hrtime()的优点是它测量时间非常精确，执行时间不到一毫秒。

**语法:**

```
process.hrtime([time])
```

**参数:**该方法接受如上所述和如下所述的单个参数。

*   **时间:**时间是一个**可选参数** r，它必须是前一个进程的结果。hrtime()调用与当前时间的差值。

**返回类型:**返回一个包含 2 个*整数的数组。*该 1。 *int* 包含秒和 2。 *int* 纳秒。这些时间是相对于过去的任意时间，与一天中的时间无关。

**例 1:**

## java 描述语言

```
// Implement the function..

var hrTime = process.hrtime()

// Time in millisecond...
console.log("Time in millisecond is: ", hrTime[0] * 1000 + hrTime[1] / 1000000)
```

**输出:**

```
Time in millisecond is:  218394926745.5
```

**例 2:**

## java 描述语言

```
// Create a variable and call the process.hrtime() function.
var start_time = process.hrtime();

// Print the Start time:
console.log("Start Time:",start_time);

// Make the add function
setTimeout(function(){

// Create two variable
var a = '40',
b = '50';

// Print the Addition result:
console.log("Add of two number is :",(a - 0) + (b - 0));

    // Create a variable and call the second process.hrtime()
    // function and pass the start time as parameter.
    var end_time = process.hrtime(start_time);
    // Print the Execution time.
    console.log("End Time:",end_time);

}, 1000);
```

**输出:**表示 1 秒，从开始到结束耗时 8779100 纳秒。

```
Start Time: [ 682340, 452477300 ]
Add of two number is : 90
End Time: [ 1, 8779100 ]
```

**例 3:**

## java 描述语言

```
// Create a variable and call the process.hrtime() function.
var start_time = process.hrtime();

// Print the Start time:
console.log("Start Time:",start_time);

// Make the add function
setTimeout(function(){

    console.log("Execution time will be calculated"+
                " for printing this message....");

    // Create a variable and call the second process.hrtime()
    // function and pass the start time as.
    var end_time = process.hrtime(start_time);
    // Print the Execution time.
    console.log("End Time:",end_time);

}, 1000);
```

**输出:**表示 1 秒，从开始到结束时间取 10987200 纳秒。

```
Start Time: [ 682865, 516565300 ]
Execution time will be calculated for printing this message....
End Time: [ 1, 10987200 ]
```

**参考摄:**[https://nodejs . org/API/process . html # process _ process _ HR time _ time](https://nodejs.org/api/process.html#process_process_hrtime_time)