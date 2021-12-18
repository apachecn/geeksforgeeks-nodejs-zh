# 如何在 Node.js 中不用循环对数组进行排序？

> 原文:[https://www . geesforgeks . org/如何在不使用节点循环的情况下对数组进行排序-js/](https://www.geeksforgeeks.org/how-to-sorting-an-array-without-using-loops-in-node-js/)

***【设置间隔()*** 方法在每个给定的时间间隔重复或重新安排给定的功能。这有点像 JavaScript API 的 *window.setInterval()* 方法，但是不能传递一串代码让它执行。

**语法:**

```
setInterval(timerFunction, millisecondsTime);
```

**参数:**接受上面提到的，下面描述的两个参数:

*   **[timer function]** < *Function* > **:** is the function to be executed.
*   **millisecond time** < *Time* >: it means the time between each execution.

***setTimeout()*** 方法用于调度等待指定毫秒数后的代码执行。有点像 JavaScript API 的 *window.setTimeout()* 方法，但是不能通过一串代码来执行。

**语法:**

```
setTimeout(timerFunction, millisecondsTime);
```

**参数:**接受上面提到的，下面描述的两个参数:

*   **timer function**<*function*>**:**是要执行的功能。

*   **毫秒时间** < *时间* > **:** 表示每次执行之间的一段时间。

**例:**

```
Input: Array = [ 46, 55, 2, 100, 0, 500 ]
Output: [0, 2, 46, 55, 100, 500]

Input: Array = [8, 9, 2, 7, 18, 5, 25]
Output: [ 2, 5, 7, 8, 9, 18, 25 ]

```

**方法:**排序需要访问每个元素，然后执行一些操作，这需要 for 循环访问这些元素。

现在在这里，我们可以使用***【set interval()***方法访问所有那些元素，并执行那些操作。

下面的代码用 JavaScript 语言说明了上述方法。

**文件名:Index.js**

```
const arr = [46, 55, 2, 100, 0, 500];
const l = arr.length;
var arr1 = [];
var j = 0;

var myVar1 = setInterval(myTimer1, 1);

function myTimer1() {
   const min = Math.min.apply(null, arr);
   arr1.push(min);

   // arr[arr.indexOf(min)]=Math.max.apply(null, arr);
   arr.splice(arr.indexOf(min), 1);
   j++;

   if(j == l){
     clearInterval(myVar1);    
     console.log(arr1);
   }
}
```

在在线编译器上运行 **Index.js** 文件，或者按照以下步骤操作:

```
node index.js
```

**输出:**

```
[0, 2, 46, 55, 100, 500]

```