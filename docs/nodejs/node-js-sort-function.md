# Node.js sort()函数

> 原文:[https://www.geeksforgeeks.org/node-js-sort-function/](https://www.geeksforgeeks.org/node-js-sort-function/)

**sort()** 是来自 [Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 的数组函数，用于给定数组排序。

**语法:**

```
*array_name*.sort()
```

**参数:**该函数不取任何参数。

**返回类型:**函数返回排序后的数组。

下面的程序演示了该函数的工作原理:

**节目 1:**

```
function sortDemo()
{
  arr.sort()
  console.log(arr);
}
var arr=[ 3, 1, 8, 5, 2, 1];
sortDemo();
```

**输出:**

```
[ 1, 1, 2, 3, 5, 8 ]
```

**节目 2:**

```
function sortDemo()
{
  arr.sort()
  console.log(arr);
}
var arr=[ -3, 1, 10, 12, 1];
sortDemo();
```

**输出:**

```
[ -3, 1, 1, 10, 12 ]
```