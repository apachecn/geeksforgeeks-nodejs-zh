# Node.js forEach()函数

> 原文:[https://www.geeksforgeeks.org/node-js-foreach-function/](https://www.geeksforgeeks.org/node-js-foreach-function/)

**forEach()** 是来自 [Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 的数组函数，用于迭代给定数组中的项。

**语法:**

```
*array_name*.forEach(*function*)
```

**参数:**该函数以一个函数(待执行)为参数。

**返回类型:**函数迭代后返回数组元素。

下面的程序演示了该函数的工作原理:

**节目 1:**

```
const arr = ['cat', 'dog', 'fish'];
arr.forEach(element => {
  console.log(element);
});
```

**输出:**

```
cat
dog
fish
```

**节目 2:**

```
const arr = [1, 2, 3, 8, 7];
arr.forEach(element => {
  console.log(element);
});
```

**输出:**

```
1
2
3
8
7
```