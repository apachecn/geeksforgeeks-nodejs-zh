# Node.js Buffer.readDoubleBE()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-readdouble be-method/](https://www.geeksforgeeks.org/node-js-buffer-readdoublebe-method/)

Node.js 中的 **Buffer.readDoubleBE()方法**用于以大端格式从给定偏移量的缓冲区中读取 64 位双精度值。

**语法:**

```js
Buffer.readDoubleBE( offset )
```

**参数:**该方法接受单参数**偏移量**，该偏移量保存开始读取前要跳过的字节数。偏移值介于 **0 < =偏移<= buf . length–8**之间。其默认值为 0。

**返回值:**以大端格式返回整数值。

下面的例子说明了 buf.readDoubleBE()方法在 Node.js 中的使用:

**例 1:**

```js
// Node program to demonstrate the  
// Buffer.readDoubleBE() method 

// Creating a buffer of given size 
const buf = Buffer.from([10, 20, 30, 40, 50, 60, 70, 80]);

// Display the result 
console.log("Functions of Buffer.readDoubleBe(int)");
console.log(buf.readDoubleBE(0))
console.log(buf); 
```

**输出:**

```js
Functions of Buffer.readDoubleBe(int)
4.0888790063059496e-260
<Buffer 0a 14 1e 28 32 3c 46 50>
```

**例 2:**

```js
// Node program to demonstrate the  
// Buffer.readDoubleBE() method 

// Creating a buffer of given size 
const buf = Buffer.from([100, 200, 300, 400, 500, 600, 700, 800]);

// Display the result 
console.log("Functions of Buffer.readDoubleBe(int)"); 
console.log(buf.readDoubleBE(5))
console.log(buf); 
```

**输出:**

```js
Functions of Buffer.readDoubleBe(int)
internal/buffer.js:72
  throw new ERR_OUT_OF_RANGE(type || 'offset',
  ^

RangeError [ERR_OUT_OF_RANGE]: The value of "offset" is out of range.
It must be >= 0 and <= 5 0\. received . .< pre>**注意:**以上程序使用`node index.js`命令编译运行。**参考:**T2【https://nodejs . org/docs/latest-v 11 . x/API/buffer . html # buffer _ buf _ readdouble be _ offset=>
```