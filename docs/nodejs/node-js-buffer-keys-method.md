# Node.js Buffer.keys()方法

> 原文:[https://www.geeksforgeeks.org/node-js-buffer-keys-method/](https://www.geeksforgeeks.org/node-js-buffer-keys-method/)

**Buffer.keys()方法**用于返回一个迭代器对象，包含缓冲对象中每个字节的键。

**语法:**

```js
Buffer.keys()
```

**参数:**此方法不接受任何参数。

**返回值:**它返回一个迭代器对象，该对象具有缓冲区的键。

**例 1:**

```js
// Node.js program to demonstrate the   
// Buffer.keys() method  
var buf = Buffer.from('Hello World');

// Read in the iterator object
// and return the key number
for (index of buf.keys()) {
      console.log(index);
}
```

**输出:**

```js
0
1
2
3
4
5
6
7
8
9 

```

**例 2:**

```js
// Node.js program to demonstrate the
// Buffer.keys() method
var buf1 = Buffer.from('abc');
var buf2 = Buffer.from('1');

// Read in the first iterator object
// and return the key number
for(index of buf1.keys()) {
    console.log(index);
}

// Read in the first iterator object
// and return the key number
for(index of buf2.keys()) {
    console.log(index)
}
```

**输出:**

```js
0
1
2
0

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**T2】https://nodejs.org/api/buffer.html#buffer_buf_keys