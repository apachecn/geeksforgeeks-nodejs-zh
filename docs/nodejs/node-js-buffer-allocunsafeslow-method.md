# node . js buffer . allocansafeslow()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-allocunsafeslow-method/](https://www.geeksforgeeks.org/node-js-buffer-allocunsafeslow-method/)

**缓冲区**是一个临时存储器，当数据从一个地方移动到另一个地方时，它存储数据。就像整数数组。**buffer . allocansafeslow()**方法分配给定大小的新缓冲实例，但不初始化它。

Buffer.allocUnsafeSlow()方法用于分配给定大小的新缓冲区(以字节为单位)。如果给定的大小大于 buffer.constants.MAX_LENGTH 或小于 0，将引发 ERR_INVALID_OPT_VALUE。如果大小为零，则创建零长度缓冲区。

此方法不同于 Buffer.allocUnsafe()方法。在 allocUnsafe()方法中，如果缓冲区大小小于 4KB，它会自动从预先分配的缓冲区中切出所需的缓冲区，即不会初始化新的缓冲区。它通过不分配许多小的缓冲实例来节省内存。但是如果开发人员需要在中间时间内保留一定量的开销内存，那么可以使用**allocansafeslow()**方法。

**语法:**

```
buffer.allocUnsafeSlow( size )
```

**参数:**该方法接受单个参数**大小**，它保存所需的缓冲区大小。

**注意:**如果大小不是数字，这个方法会抛出一个 TypeError。

以下示例说明了**buffer . allocansafeslow()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the  
// Buffer.allocUnsafeSlow() Method

// Creating a buffer
const buffer = Buffer.allocUnsafe(10); 

// Display the buffer containing random values 
console.log("allocUnsafeSlow() Method"); 
console.log(buffer);
```

**输出:**

```
allocUnsafeSlow() Method
<Buffer 01 00 00 00 00 00 00 00 8b ed>
```

**例 2:**

```
// Node.js program to demonstrate the  
// Buffer.allocUnsafeSlow() Method

// Creating a buffer
const buffer = Buffer.allocUnsafe(4); 

// Print: random string everytime we run the
// program as we have not added
// anything to the buffer yet
console.log(buffer.toString());

for (let i = 0; i < 4; i++) {

    //filling the values in buffer
    buffer[i] = i + 97;
}

// Adds and Print: 'abcd' as 97 98 99 100 101
// are their respective ASCII values
console.log(buffer.toString());
```

**输出:**

```
rite
abcd
```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buffer _ class _ method _ buffer _ allocansafeslow _ size](https://nodejs.org/api/buffer.html#buffer_class_method_buffer_allocunsafeslow_size)