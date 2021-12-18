# Node.js Buffer.equals()方法

> 原文:[https://www.geeksforgeeks.org/node-js-buffer-equals-method/](https://www.geeksforgeeks.org/node-js-buffer-equals-method/)

**Buffer.equals()方法**用于比较两个缓冲区对象，如果两个缓冲区对象相同，则返回真，否则返回假。

**语法:**

```js
buffer.equals( buf )
```

**参数:**该方法接受单个参数 **otherBuffer** ，保存另一个缓冲区与缓冲区对象进行比较。

**返回值:**如果两个缓冲区对象相等，该方法返回真，否则返回假。

以下示例说明了 Node.js 中的 **Buffer.equals()方法**:

**例 1:**

```js
// Node.js program to demonstrate the   
// Buffer.equals() Method

// Create two bufferes
var buf1 = Buffer.from('Hi');
var buf2 = Buffer.from('Hi');

// Prints true(boolean value)
console.log(buf1.equals(buf2));
```

**输出:**

```js
true
```

**例 2:**

```js
// Node.js program to demonstrate the   
// Buffer.equals() Method

// Create two bufferes
var buf1 = Buffer.from('Hi');
var buf2 = Buffer.from('Hello');

// Prints false(boolean value)
console.log(buf1.equals(buf2));
```

**输出:**

```js
false
```

**参考:**[https://nodejs . org/API/buffer . html # buffer _ buf _ equals _ other buffer](https://nodejs.org/api/buffer.html#buffer_buf_equals_otherbuffer)