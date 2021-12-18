# Node.js unshift()功能

> 原文:[https://www.geeksforgeeks.org/node-js-unshift-function/](https://www.geeksforgeeks.org/node-js-unshift-function/)

**unshift()** 是来自 [Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 的数组函数，用于将元素插入到数组的前面。

**语法:**

```js

*array_name*.unshift(*element*)

```

**参数:**该函数接受必须添加到数组中的参数。它还可以将多个元素作为参数。

**返回类型:**函数在添加元素后返回数组。

下面的程序演示了该函数的工作原理:

**节目 1:**

```js
function unshiftDemo()
{
  var element = arr.unshift(12);
  console.log(arr);
}
var arr=[1, 5, 7, 9, 78];
unshiftDemo();
```

**输出:**

```js
[12,1,5,7,9,78]
```

**节目 2:**

```js
function addLang()
{
  var element = arr.unshift("Node.js","php");
  console.log(arr);
}
var arr=[ "C", "Java", "JavaScript", "Python" ];
addLang();
```

**输出:**

```js
[ 'Node.js', 'php', 'C', 'Java', 'JavaScript', 'Python' ]
```