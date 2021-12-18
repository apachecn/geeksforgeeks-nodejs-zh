# 为什么我们在 Node.js 中使用 setTimeout()函数？

> 原文:[https://www . geesforgeks . org/why-we-use-settimeout-function-in-node-js/](https://www.geeksforgeeks.org/why-we-use-settimeout-function-in-node-js/)

setTimeout 函数的目的是在一定时间间隔后执行一段代码。setTimeout()函数接受两个参数。第一个参数是函数，第二个参数是以毫秒为单位的时间。setTimeout()在第二个参数中指定的时间之后执行第一个参数中传递的函数。setTimeout 函数不会阻塞其他代码，其余代码将被执行，并且在指定时间后，setTimeout 函数内部的代码将被执行。

**语法:**

```js
setTimeout( function , time_in_milliseconds )
```

**示例 1:** 在本例中，定义了一个函数，然后将该函数作为 setTimeout()函数的第一个参数传递。第二个参数以毫秒为单位指定时间延迟，即 3000。因此，函数内部的代码将在 3000 毫秒后执行，程序中的其余代码将被执行。

## Javascript

```js
<script>
    printStatement = () => {
        console.log('Printed after 3 seconds');
    }
    setTimeout(printStatement, 3000);
    console.log('Printed Immediately');
</script>
```