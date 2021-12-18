# Node.js Buffer.isBuffer()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-is buffer-method/](https://www.geeksforgeeks.org/node-js-buffer-isbuffer-method/)

缓冲区是一种临时内存存储，当数据从一个地方移动到另一个地方时，它存储数据。它就像一个整数数组。

**Buffer.isBuffer()方法**检查提供的对象是否是缓冲区。

**语法:**

```
Buffer.isBuffer( obj )
```

**参数:**该方法接受单个参数 **obj** ，需要检查是否为缓冲区。

**返回值:**这个方法返回一个布尔值， **true** 如果对象是缓冲区，否则返回 **false** 。

下面的例子说明了 **Buffer.isBuffer()** 方法在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the  
// Buffer.isBuffer() Method

var buffer = Buffer.from('GeeksForGeeks');

console.log(Buffer.isBuffer(buffer));
```

**输出**

```
true
```

**例 2:**

```
// Node.js program to demonstrate the  
// Buffer.isBuffer()) Method

var buf1 = "GeeksforGeeks"; 

console.log(Buffer.isBuffer(buf1));

var buf2 = new Buffer(4);

for (var i = 0 ; i < 4 ; i++) {
    buf2[i] = i + 97;
}

// Prints: abcd
// as 97, 98, 99, 100 are the ASCII 
// values of these chars respectively

console.log(buf2.toString());

console.log(Buffer.isBuffer(buf2));
// Prints: true
```

**输出:**

```
false
abcd
true

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buffer _ class _ method _ buffer _ is buffer _ obj](https://nodejs.org/api/buffer.html#buffer_class_method_buffer_isbuffer_obj)