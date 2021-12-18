# Node.js join()函数

> 原文:[https://www.geeksforgeeks.org/node-js-join-function/](https://www.geeksforgeeks.org/node-js-join-function/)

**join()** 是来自 [Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 的数组函数，用于从数组中返回一个字符串。

**语法:**

```js
*array_name*.join(*parameter*)
```

**参数:**该函数采用单个参数，根据该参数必须执行连接操作。

**返回类型:**函数返回字符串。

下面的程序演示了功能的工作:
**程序 1:**

```js
function joinDemo()
{
  var str= arr.join("*");
  console.log(str);
}
var arr=[17, 55, 87, 49, 78];
joinDemo();
```

**输出:**

```js
17*55*87*49*78
```

**程序 2:**

```js
function joinDemo()
{
  var str= arr.join("");
  var str1= arr.join("{content}quot;);
  console.log(str);
  console.log(str1);  
}
var arr=['C','Java','Python'];
joinDemo();
```

**输出:**

```js
CJavaPython
C$Java$Python
```