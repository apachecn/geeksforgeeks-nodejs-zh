# 如何在 Node.js 中不使用任何循环搜索一个元素？

> 原文:[https://www . geesforgeks . org/如何在不使用任何节点循环的情况下搜索元素-js/](https://www.geeksforgeeks.org/how-to-search-an-element-without-using-any-loops-in-node-js/)

***【设置间隔()*** 方法在每个给定的时间间隔重复或重新安排给定的功能。这有点像 JavaScript API 的 *window.setInterval()* 方法，但是不能传递一串代码让它执行。

**语法:**

```
setInterval(timerFunction, millisecondsTime);

```

**参数:**接受上面提到的和下面描述的两个参数:

*   **定时器功能<功能> :** 是要执行的功能。
*   **毫秒时间<时间> :** 表示每次执行之间的时间间隔。

*clearInterval()* 方法用于停止下一个调度代码执行。这有点像 JavaScript API 的 *window.clearInterval()* 方法，但是不能传递一串代码让它执行。

**语法:**

```
clearInterval(intervalVar);

```

参数:它接受上面提到的和下面描述的单个参数:

*   **interval**<*函数* >:是下一个区间需要停止执行的函数名。

**示例:**

```
Input: Array = [ 46, 55, 2, 100, 0, 500 ]
Search Element = 0

Output: Element 0 found at index 4

Input: Array = [8, 9, 2, 7, 18, 5, 25]
Search Element = 500

Output: Element 500 not found in Array.

```

**方法:**排序需要访问每个元素，然后执行一些操作，这需要 for 循环访问这些元素。

现在在这里，我们可以使用 *setInterval()* 方法访问所有那些元素并执行那些操作。

下面的代码用 JavaScript 语言说明了上述方法。

**例 1:** **文件名:Index.js**

```
// Node.js program to search an element 
// without using any loops provided Array

const arr = [46, 55, 2, 100, 0, 500];
const l = arr.length;
var j = 0;

// Element to Search
var srchElement = 0;

// setInterval for looping purpose 
var myVar1 = setInterval(myTimer1, 1);

function myTimer1() {
    if (arr[j] == srchElement) {

        // Clear interval as required 
        // element is found 
        clearInterval(myVar1);

        // Printing found element
        console.log("Element", srchElement, 
            "found at index", arr.indexOf(arr[j]));
    }

    j++;

    if (j == l) {
        // Clear interval as element
        // not found in array
        clearInterval(myVar1);

        // Printing that element not found
        console.log("Element", srchElement, 
                    "not found in Array.");
    }
} 
```

在在线编译器上运行 **index.js** 文件，或者按照以下步骤操作:

```
node index.js
```

**输出:**

```
在索引 4 处找到元素 0
```

**例 2:** **文件名:index.js**

```
// Node.js program to search an element 
// without using any loops provided Array

const arr = [8, 9, 2, 7, 18, 5, 25];
const l = arr.length;
var j = 0;

// Element to Search
var srchElement = 50;

// setInterval for looping purpose 
var myVar1 = setInterval(myTimer1, 1);

function myTimer1() {

    if (arr[j] == srchElement) {

        // Clear interval as required
        // element is found 
        clearInterval(myVar1);

        // Printing found element
        console.log("Element", srchElement, 
            "found at index", arr.indexOf(arr[j]));
    }

    j++;

    if (j == l) {

        // clear interval as element not
        // found in array
        clearInterval(myVar1);

        // Printing that element not found
        console.log("Element", srchElement, 
                "not found in Array.");
    }
} 
```

在在线编译器上运行 **index.js** 文件，或者按照以下步骤操作:

```
node index.js

```

**输出:**

```
数组中找不到元素 50。
```