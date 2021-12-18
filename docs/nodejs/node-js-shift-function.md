# Node.js shift()功能

> 原文:[https://www.geeksforgeeks.org/node-js-shift-function/](https://www.geeksforgeeks.org/node-js-shift-function/)

**shift()** 是来自 [Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 的数组函数，用于删除数组前面的元素。

**语法:**

```
*array_name*.shift()
```

**参数:**该函数不取任何参数。

**返回类型:**函数删除元素后返回数组。

下面的程序演示了该函数的工作原理:

**程序 1:**

```
function shiftDemo()
{
  arr.shift();
  console.log(arr);
}
var arr=[17, 55, 87, 49, 78];
shiftDemo();
```

**输出:**

```
[ 55, 87, 49, 78 ]
```

**程序 2:**

```
function shiftDemo()
{
  arr.shift();
  console.log(arr);
}
var arr=['a', 'b'];
shiftDemo();
```

**输出:**

```
[ 'b' ]
```

**程序 3:**

```
let Lang = ["Python", "C", "Java", "JavaScript"];
while ((i = Lang.shift()) !== undefined) {
    Lang.shift();
}
console.log(Lang);
```

**输出:**

```
[]
```