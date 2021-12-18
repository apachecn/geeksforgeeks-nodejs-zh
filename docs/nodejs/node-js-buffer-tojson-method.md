# Node.js Buffer.toJSON()方法

> 原文:[https://www.geeksforgeeks.org/node-js-buffer-tojson-method/](https://www.geeksforgeeks.org/node-js-buffer-tojson-method/)

缓冲区是一种临时内存存储，当数据从一个地方移动到另一个地方时，它存储数据。它就像整数数组。

**Buffer.toJSON()方法**以 JSON 格式返回缓冲区。

**注:**JSON。Stringify()是也可以用来返回 JSON 格式数据的方法。当我们调用 JSON 时。Stringify()方法，它直接在后台调用 buffer.toJSON()方法。

**语法:**

```js
buffer.toJSON()
```

**返回值:**以 JSON 格式返回缓冲区。

下面的例子说明了 **Buffer.toJSON()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the  
// Buffer.toJSON() Method

var buffer = Buffer.from('GeeksforGeeks');

// Prints: the ascii values of each
// character of 'GeeksforGeeks'
console.log(buffer.toJSON());
```

**输出:**

```js
{
  type: 'Buffer',
  data: [
     71, 101, 101, 107,
    115, 102, 111, 114,
     71, 101, 101, 107,
    115
  ]
}

```

**示例 2:** 这个示例实现了 JSON 的使用。Stringify()方法。

```js
// Node.js program to demonstrate the  
// Buffer.toJSON() Method

const buffer = Buffer.from([1, 2, 3, 4]);

const output = JSON.stringify(buffer);

// Prints: {"type":"Buffer", "data":[1, 2, 3, 4]}
console.log(output);
```

**输出:**

```js
{"type":"Buffer", "data":[1, 2, 3, 4]}
```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buffer _ buf _ tojson](https://nodejs.org/api/buffer.html#buffer_buf_tojson)