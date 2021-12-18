# Node.js pop()功能

> 原文:[https://www.geeksforgeeks.org/node-js-pop-function/](https://www.geeksforgeeks.org/node-js-pop-function/)

**pop()** 是来自 [Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 的数组函数，用于从数组末尾移除元素。

**语法:**

```
*array_name*.pop()
```

**参数:**该函数不取任何参数。

**返回类型:**函数返回数组。

下面的程序演示了该函数的工作原理:

**程序 1:**

```
function POP()
{
  arr.pop();
  console.log(arr);
}
var arr = [1,2,3,4,5,6,7];
POP();
```

输出:

```
[ 1, 2, 3, 4, 5, 6 ]

```

**程序 2:**

```
function POP()
{
  arr.pop();
  console.log(arr);
}
var arr = ['GFG'];
POP();
```

输出:

```
[]

```

**程序 3:**

```
var Lang = ['java', 'c', 'python'];

console.log(Lang);
// expected output: Array [ 'java', 'c', 'python' ]

Lang.pop();

console.log(Lang);
// expected output: Array [ 'java', 'c' ]
```

**输出:**

```
[ 'java', 'c', 'python' ]
[ 'java', 'c' ]
```