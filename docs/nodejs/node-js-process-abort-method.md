# Node.js process.abort()方法

> 原文:[https://www.geeksforgeeks.org/node-js-process-abort-method/](https://www.geeksforgeeks.org/node-js-process-abort-method/)

**process.abort()** 属性是流程模块的内置应用编程接口，用于立即中止正在运行的 NodeJS 流程。它还生成一个核心文件。

**语法:**

```
process.abort()
```

**参数:**本功能不接受任何参数。

**返回类型:**有空返回类型。

下面的例子说明了 Node.js 中 process.abort()属性的使用:

**例 1:**

## index . js

```
// Function to illustrate abort method
const RunWithAbort = () => {
    console.log('Start...');

    // It prints GeeksForGeeks after every 1 second
    setInterval((function() {
        return console.log('GeeksForGeeks');
    }), 1000);

    // It calls process.abort() after 5 seconds
    setTimeout((function() {
        return process.abort();
    }), 5000);
};

// Function to illustrate working of above function 
// without abort method
const RunWithoutAbort = () => {
    console.log('Start...');

    // It prints GeeksForGeeks after every 1 second
    setInterval((function() {
        return console.log('GeeksForGeeks');
    }), 1000);
};

// Uncomment below line to call RunWithoutAbort
// function it will run in infinitely
// RunWithoutAbort();

// Call RunWithAbort function
// it will abort after 5 seconds
RunWithAbort();
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**我们将在控制台屏幕上看到以下输出。

```
Start...
GeeksForGeeks
GeeksForGeeks
GeeksForGeeks
GeeksForGeeks
Abort trap: 6
```

**例 2:**

## index . js

```
// Function to illustrate abort method
const RunWithAbort = () => {
    console.log('Start...');

    // It prints GeeksForGeeks after every 1 second
    setInterval((function() {
        return console.log('GeeksForGeeks : 1 second');
    }), 1000);

    // It prints GeeksForGeeks after every 2 seconds
    setInterval((function() {
        return console.log('GeeksForGeeks : 2 second');
    }), 2000);

    // It calls process.abort() after 5 seconds
    setTimeout((function() {
        return process.abort();
    }), 5000);
};

const RunWithoutAbort = () => {
    console.log('Start...');

    // It prints GeeksForGeeks after every 1 second
    setInterval((function() {
        return console.log('GeeksForGeeks');
    }), 1000);
};

// Uncomment below line to call RunWithoutAbort
// function it will run in infinitely
// RunWithoutAbort();

// Call RunWithAbort function
// it will abort after 5 seconds
RunWithAbort();
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**我们将在控制台屏幕上看到以下输出。

```
Start...
GeeksForGeeks : 1 second
GeeksForGeeks : 2 second
GeeksForGeeks : 1 second
GeeksForGeeks : 1 second
GeeksForGeeks : 2 second
GeeksForGeeks : 1 second
Abort trap: 6
```

**参考:**T2】https://nodejs.org/api/process.html#process_process_abort