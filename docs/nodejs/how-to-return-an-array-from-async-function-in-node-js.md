# 如何从 Node.js 中的异步函数返回数组？

> 原文:[https://www . geesforgeks . org/如何从节点中的异步函数返回数组-js/](https://www.geeksforgeeks.org/how-to-return-an-array-from-async-function-in-node-js/)

我们必须从另一个异步或同步的函数中调用异步函数(我们可以传递数组或选择在异步函数本身中声明数组)，然后从异步函数中返回数组。

基本的方法是包含一个 try-catch 块。如果在执行 try block 语句时发生任何错误，则使用 catch 块来处理异常。

**例 1:** 下面是我们调用*打印*功能的代码。我们在这个函数中定义数组(在这个例子中是异步的)，把它传递给另一个异步函数*排序*。*排序*功能然后对数组进行排序并返回数组，然后我们从*打印*功能显示数组。

## index.js

```
const sort = async (arr) => {
    try {
        let i, j, temp;

        // Using bubble sort to sort the array 
        for (i = 0; i < arr.length; i++) {
            for (j = i + 1; j < arr.length; j++) {
                if (arr[i] > arr[j]) {

                    // The await prevents the 
                    // execution of next line 
                    // until this line is executed
                    temp = await arr[i];
                    arr[i] = await arr[j];
                    arr[j] = await temp;
                }
            }
        }

        // Returns the sorted array
        return arr;
    }
    catch (e) {

        // Display the error in case
        // enything wrong happened
        console.log(e)
    }
}

const print = async () => {

    // Use try-catch block to handle error
    try {

        // Define and initialize an array
        let arr = [17, 90, 13, 10, 76]

        // Call the "sort" function passing
        // the array and store the result in
        // "sortedArray", await will prevent
        // the execution of next line until
        // this line is executed.
        const sortedArray = await sort(arr)

        // Display sortedArray to check if 
        // everything works fine
        console.log(sortedArray)
    }
    catch (e) {

        // Display the error in case 
        // anything wrong happened
        console.log(e)
    }
}

// Calling print() is called
print();
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
[ 10, 13, 17, 76, 90 ]
```

**示例 2:** 现在让我们看看从异步函数返回数组的示例，该异步函数已在该异步函数中声明。该函数将返回一个由小于给定数 n 的所有素数组成的数组

## index.js

```
const prime = async (N) => {
    try {
        const arr = []

        // Iterate from 2 to N-1 to check
        // which numbers are prime
        for (var i = 2; i < N; i++) {
            let j = 2
            while (j < i) {
                // Check if the number is 
                // divisble by any number
                // except 1 and itself
                if (i % j == 0) {
                    break
                }
                j++;
            }
            if (j == i) {
                // If this condition holds 
                // true then it means that
                // the number is not 
                // divisible by any number
                // except 1 and itself. 
                // Therefore, it is a prime 
                // number and add this number
                // to the array.
                arr.push(j)
            }
        }

        // Return the array
        return arr
    }
    catch (e) {

        // Display the error in case
        // anything wrong happened
        console.log(e)
    }
}

const findPrime = async () => {
    try {
        let N = 20

        // Call prime() passing argument
        // N which is equal to 20 and 
        // store the result in an array
        const primeAry = await prime(N)

        // Print the array
        console.log(primeAry)
    }
    catch (e) {

        // Display the error in case
        // anything wrong happened
        console.log(e)
    }
}

// Calling findPrime() method
findPrime()
```

**输出:**

```
[
   2,  3,  5,  7,
   11, 13, 17, 19 
]
```