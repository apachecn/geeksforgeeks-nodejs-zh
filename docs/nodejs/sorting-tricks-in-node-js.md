# node . js 中的排序技巧

> 原文:[https://www.geeksforgeeks.org/sorting-tricks-in-node-js/](https://www.geeksforgeeks.org/sorting-tricks-in-node-js/)

**使用定时器类对数组进行排序:**

**方法:**排序需要访问每个元素，然后执行一些操作，这需要 for 循环访问这些元素。

现在在这里，我们可以使用 *setInterval()* 方法访问所有那些元素，并执行那些操作。并且在访问期间，我们可以使用 *setTimer()* 方法访问所有元素，并打印该时间段内数组的最小值。

**设置间隔()**方法在每个给定的时间间隔重复或重新安排给定的功能。这有点像 JavaScript API 的 *window.setInterval()* 方法，但是不能传递一串代码让它执行。

**语法:**

```js
setInterval(timerFunction, millisecondsTime);
```

**参数:**它接受上面提到的和下面描述的两个参数:

*   **定时器功能** < *功能* >:是需要执行的功能。
*   **毫秒时间** < *时间* >:表示每次执行之间的一段时间。

**setTimeout()** 方法用于调度等待指定毫秒数后的代码执行。有点像 JavaScript API 的 *window.setTimeout()* 方法，但是不能传递一串代码来执行。

**语法:**

```js
setTimeout(timerFunction, millisecondsTime);
```

**参数:**接受上面提到的和下面描述的两个参数:

*   **定时器功能** < *功能* >:是需要执行的功能。
*   **毫秒时间** < *时间* >:表示每次执行之间的一段时间。

**示例:**

```js
Input: Array = [ 46, 55, 2, 100, 0, 500 ]
Output: [0, 2, 46, 55, 100, 500]

Input: Array = [8, 9, 2, 7, 18, 5, 25]
Output: [ 2, 5, 7, 8, 9, 18, 25 ]
```

**例 1:** **文件名:Index.js**

```js
const arr = [10, 50, 100, 500, 0, 200];
var arr1 = [];

function sortIt() {
for (let i of arr) {

 // setTimeout(()=> console.log(i), i)

 setTimeout(()=> {

   arr1.push(i);
   arr.splice(arr.indexOf(i), 1);
   if(arr.length === 0){
     console.log(arr1);
   }
 }, i)
}}

sortIt();
```

**输出:**

```js
[ 0, 10, 50, 100, 200, 500 ]
```

**例 2:** **文件名:Index.js**

```js
const arr = [10, 50, 100, 500, 0, 200];
var arr1 = [];

function sortIt() {
   for (let i of arr) {
     // setTimeout(()=> console.log(i), i)
     setTimeout(()=> {

        arr1.push(i);
        i = Math.max.apply(null, arr);

        // arr.splice(arr.indexOf(i), 1);
        if(arr1.length === arr.length) {
           console.log(arr1);
        }
     }, i)
}}

sortIt();
```

使用以下命令运行 **Index.js** 文件。

```js
node index.js
```

**输出:**

```js
[ 0, 10, 50, 100, 200, 500 ]
```