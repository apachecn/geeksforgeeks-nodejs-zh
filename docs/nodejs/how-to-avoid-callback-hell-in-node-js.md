# 如何避免 Node.js 中的回调地狱？

> 原文:[https://www . geesforgeks . org/如何避免回调-地狱节点-js/](https://www.geeksforgeeks.org/how-to-avoid-callback-hell-in-node-js/)

Node.js 中[回调地狱](https://www.geeksforgeeks.org/what-is-callback-hell-in-node-js/)就是我们有复杂嵌套回调的情况。在这种情况下，每个回调都采用作为先前回调的结果而获得的参数。这种回调结构导致代码可读性和可维护性较差。

借助[承诺](https://www.geeksforgeeks.org/javascript-promises/)，我们可以避免回调地狱。javascript 中的承诺是在 Node.js 中处理异步操作的一种方式，它允许我们像同步函数一样从异步函数中返回值。当我们从异步方法中返回一些东西时，它会返回一个承诺，当将来在异步函数内部的[然后()](https://www.geeksforgeeks.org/why-we-use-then-method-in-javascript/)方法或[等待](https://www.geeksforgeeks.org/async-await-function-in-javascript/)的帮助下，这个承诺可以用来消费最终值。下面提到了创建承诺的语法。

```js
const promise = new Promise(function(resolve, reject){
     // code logic
});
```

**示例:**在下面提到的代码示例中，我们在 [setTimeout()](https://www.geeksforgeeks.org/what-is-the-purpose-of-settimeout-function-in-javascript/) 的帮助下模拟了一个异步添加操作。

*   首先，我们创建一个 add()函数，该函数接受三个参数，其中两个参数是我们要添加的数字，第三个参数是回调函数，该函数在 2 秒钟后用 add 操作的结果调用。然后，我们使用嵌套回调来模拟回调地狱，计算前四个自然数相加的结果。
*   之后，我们创建一个返回承诺的 addPromise()函数，这个承诺在调用该函数两秒钟后得到解决。然后我们使用 Then()方法和 async/await 来消费承诺。

## java 描述语言

```js
// The callback function for function
// is executed after two seconds with
// the result of addition
const add = function (a, b, callback) {
  setTimeout(() => {
    callback(a + b);
  }, 2000);
};

// Using nested callbacks to calculate
// the sum of first four natural numbers.
add(1, 2, (sum1) => {
  add(3, sum1, (sum2) => {
    add(4, sum2, (sum3) => {
      console.log(`Sum of first 4 natural 
      numbers using callback is ${sum3}`);
    });
  });
});

// This function returns a promise
// that will later be consumed to get
// the result of addition
const addPromise = function (a, b) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve(a + b);
    }, 2000);
  });
};

// Consuming promises with the chaining of then()
// method and calculating the result
addPromise(1, 2)
  .then((sum1) => {
    return addPromise(3, sum1);
  })
  .then((sum2) => {
    return addPromise(4, sum2);
  })
  .then((sum3) => {
    console.log(
      `Sum of first 4 natural numbers using 
       promise and then() is ${sum3}`
    );
  });

// Calculation the result of addition by
// consuming the promise using async/await
(async () => {
  const sum1 = await addPromise(1, 2);
  const sum2 = await addPromise(3, sum1);
  const sum3 = await addPromise(4, sum2);

  console.log(
    `Sum of first 4 natural numbers using 
     promise and async/await is ${sum3}`
  );
})();
```

**输出:**

![](img/c0d9a0bca7d616ceedc97e98cf72b7c2.png)