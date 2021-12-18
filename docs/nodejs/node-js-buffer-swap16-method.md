# Node.js Buffer.swap16()方法

> 原文:[https://www.geeksforgeeks.org/node-js-buffer-swap16-method/](https://www.geeksforgeeks.org/node-js-buffer-swap16-method/)

**Buffer.swap16()方法**是 Buffer 模块中类 **Buffer** 的内置应用编程接口，用于就地交换缓冲字节顺序。交换是通过将缓冲区解释为 16 位数字的数组来执行的。

**语法:**

```
Buffer.swap16()
```

**参数:**此方法不接受任何参数。

**返回值:**返回对交换缓冲区的引用。

**抛出错误:**如果缓冲区长度(buf.length)不是 2 的倍数，则抛出**ERR _ INVALID _ buff _ SIZE**。

下面的例子说明了 **Buffer.swap16()** 方法在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the 
// Buffer.swap16() method 

// Creating a buffer 
const buf = Buffer.from([0x1, 0x2,
        0x3, 0x4, 0x5, 0x6, 0x7, 0x8]); 

// Display the buffer value
// before swap 
console.log(buf); 

// Using Buffer.swap16() method
buf.swap16();

// Display the result 
// after swap
console.log(buf); 
```

**输出:**

```
<Buffer 01 02 03 04 05 06 07 08>
<Buffer 02 01 04 03 06 05 08 07>

```

**示例 2:** 此示例显示此方法引发的错误。

```
// Node.js program to demonstrate the 
// Buffer.swap16() method 

// Creating a buffer 
const buf = Buffer.from([0x7, 0x5, 0x2]); 

// Display the buffer value
// before swap 
console.log(buf); 

try {
    // Using Buffer.swap16() method
    // It will throw error
    buf.swap16();

    // Display the result 
    // after swap
    console.log(buf);

}
catch(e) {
    console.log("Entering catch block");

    // Display error
    console.log(e);
}
```

**输出:**

```
<Buffer 07 05 02>
Entering catch block
RangeError [ERR_INVALID_BUFFER_SIZE]: Buffer size
must be a multiple of 16-bits
    at Buffer.swap16 (buffer.js:1042:11)
    at /home/runner/index.js:14:9
    ......

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/dist/latest-v 13 . x/docs/API/buffer . html # buffer _ buf _ swap 16](https://nodejs.org/dist/latest-v13.x/docs/api/buffer.html#buffer_buf_swap16)