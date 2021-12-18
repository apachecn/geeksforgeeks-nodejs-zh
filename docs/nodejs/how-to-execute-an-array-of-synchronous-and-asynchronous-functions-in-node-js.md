# 如何在 Node.js 中执行同步和异步函数的数组？

> 原文:[https://www . geesforgeks . org/如何执行节点中的同步和异步函数数组-js/](https://www.geeksforgeeks.org/how-to-execute-an-array-of-synchronous-and-asynchronous-functions-in-node-js/)

我们有一个函数数组，有些函数是**同步的**，有些是**异步的**。我们将学习如何按顺序执行它们。

**输入:**

```
listOfFunctions = [
    () => {
        console.log("Synchronous Function);
    },
    async () => new Promise(resolve => {
        setTimeout(() => {
            resolve(true);
            console.log("Asynchronous Function);
        }, 100);
    }),
    .
    .
    .
]
```

**方法 1:** 将所有函数视为异步函数并执行。因为在 Javascript 中，即使把同步函数当成异步函数，也没有问题。

**例:**

## index . js

```
// this is our list of functions
let listOfFunctions = [
  () => {
      console.log("Synchronous Function Called");
  },
  async () => new Promise(resolve => {
      setTimeout(() => {
          console.log("Asynchronous Function Called");
          resolve(true);
      }, 100);
  })
]

// this function will be responsible
// for executing all functions of list
let executeListOfFunctions = async(listOfFunctions) => {
  for(let func of listOfFunctions){
      await func();
  }
}

// calling main function
executeListOfFunctions(listOfFunctions);
```