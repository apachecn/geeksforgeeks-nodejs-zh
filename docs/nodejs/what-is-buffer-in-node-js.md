# node . js 中的缓冲区是什么？

> 原文:[https://www.geeksforgeeks.org/what-is-buffer-in-node-js/](https://www.geeksforgeeks.org/what-is-buffer-in-node-js/)

纯 JavaScript 非常适合 Unicode 编码的字符串，但是它不能很好地处理二进制数据。当我们在浏览器级别对数据执行操作时没有问题，但是在处理 TCP 流和对文件系统执行读写操作时，需要处理纯二进制数据。为了满足这一需求，Node.js 使用了 buffer，因此在本文中，我们将了解 Node.js 中的 Buffer

**node . js 中的 Buffers:**node . js 中的 Buffer 类用于对原始二进制数据执行操作。通常，缓冲区是指内存中的特定存储位置。缓冲区和数组有一些相似之处，但不同的是数组可以是任何类型，并且可以调整大小。缓冲区只处理二进制数据，不能调整大小。缓冲区中的每个整数代表一个字节。函数用于打印缓冲区实例。

**对 Buffer 执行** **操作的方法:**

<figure class="table">

| **None** | **Method** | **Description** |
| one | 缓冲。alloc(大小) | It creates a buffer and assigns a size to it. |
| Two | 缓冲区。来自(初始化) | It initializes the buffer with the given data. |
| three | 缓冲区。写入(数据) | It writes data into the buffer. |
| four | toString() | It reads data from the buffer and returns. |
| five | 缓冲区。是缓冲区(对象) | It checks whether the object is a buffer. |
| six | 缓冲区。长度 | It returns the length of the buffer. |
| seven | Buffer. copy (buffer, segment size) | It copies data from one buffer to another. |
| eight | 缓冲区。切片(开始，结束=缓冲区.长度) | It returns the segments of the data stored in the buffer. |
| nine | 缓冲区。concat(【缓冲区，缓冲区】) | It connects two buffers. |

</figure>

**档案名称:index . js**

## 【JavaScript】

```
// Different Method to create Buffer
var buffer1 = Buffer.alloc(100);
var buffer2 = new Buffer('GFG');
var buffer3 = Buffer.from([1, 2, 3, 4]);

// Writing data to Buffer
buffer1.write("Happy Learning");

// Reading data from Buffer
var a = buffer1.toString('utf-8');
console.log(a);

// Check object is buffer or not
console.log(Buffer.isBuffer(buffer1));

// Check length of Buffer
console.log(buffer1.length);

// Copy buffer
var bufferSrc = new Buffer('ABC');
var bufferDest = Buffer.alloc(3);
bufferSrc.copy(bufferDest);

var Data = bufferDest.toString('utf-8');
console.log(Data);

// Slicing data
var bufferOld = new Buffer('GeeksForGeeks');
var bufferNew = bufferOld.slice(0, 4);
console.log(bufferNew.toString());

// concatenate two buffer
var bufferOne = new Buffer('Happy Learning ');
var bufferTwo = new Buffer('With GFG');
var bufferThree = Buffer.concat([bufferOne, bufferTwo]);
console.log(bufferThree.toString());
```