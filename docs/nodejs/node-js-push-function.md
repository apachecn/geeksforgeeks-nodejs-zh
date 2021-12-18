# Node.js push()功能

> 原文:[https://www.geeksforgeeks.org/node-js-push-function/](https://www.geeksforgeeks.org/node-js-push-function/)

**push()** 是来自 [Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 的数组函数，用于在数组末尾添加元素。

**语法:**

```js
*array_name*.push(*element*)

```

**参数:**该函数接受必须添加到数组中的参数。它也可以包含多个元素。

**返回类型:**函数在添加元素后返回数组。

下面的程序演示了该函数的工作原理:

**程序 1:**

```js
function PUSH()
{
  arr.push(2);
  console.log(arr);
}
var arr = [12, 3, 4, 6, 7, 11];
PUSH();
```

**输出:**

```js
[ 12,  3, 4, 6, 7, 11, 2]
```

**程序 2:**

```js
function addLang()
{
arr.push('DS','Algo','JavaScript');
console.log(arr);
}
var arr = ['NodeJs'];
addLang();    
```

**输出:**

```js
[ 'NodeJs', 'DS', 'Algo', 'JavaScript' ]
```

**程序 3:**

```js
var Lang = ['java', 'c', 'python'];

console.log(Lang);
// expected output: Array [ 'java', 'c', 'python' ]

Lang.push('node');

console.log(Lang);
// expected output: Array [ 'java', 'c', 'python', 'node' ]
```

**输出:**

```js
[ 'java', 'c', 'python' ]
[ 'java', 'c', 'python', 'node' ]
```