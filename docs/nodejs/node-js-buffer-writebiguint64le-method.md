# node . js buffer . writebiguint64le()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-writebiguint64le-method/](https://www.geeksforgeeks.org/node-js-buffer-writebiguint64le-method/)

**Buffer.writeBigUInt64LE()方法**是 Buffer 模块中类 Buffer 的内置应用编程接口，用于将小端 64 位大整数值写入指定偏移量处的已分配缓冲区。

**语法:**

```
Buffer.writeBigUInt64LE( value, offset )
```

**参数:**

*   **值:**此参数指定要写入缓冲区的大整数值。它应该是一个有效的 64 位小端大整数值。当值不是这个值时，行为是未定义的。*   **offset:** It specifies the number of bytes to skip before write or simply signify the index in the buffer. The value of offset lies **0 <= offset <= Buffer.length – 8**. Its default value is 0.

    **返回值:**该方法返回一个无符号整数值，即偏移量和写入字节数之和。

    下面的例子说明了在 Node.js 中使用 Buffer.writeBigUInt64LE()方法:

    **示例 1:**
    **文件名:index.js**

    ```
    // Node.js program to demonstrate the
    // buffer.writeBigUInt64LE() method 
    const buf = Buffer.allocUnsafe(8);

    // Writing big integer value into buffer
    // by using writeBigUInt64LE() method
    buf.writeBigUInt64LE(0x01030405060708n, 0);

    // display the buffer
    console.log(buf);
    ```

    使用以下命令运行 **index.js** 文件:

    ```
    node index.js
    ```

    **输出:**

    ```
    <Buffer 08 07 06 05 04 03 01 00>

    ```

    **示例 2:**
    **文件名:index.js**

    ```
    // Node.js program to demonstrate the
    // buffer.writeBigUInt64LE() method 
    const buf = Buffer.allocUnsafe(8);

    // writing big integer value into buffer
    // by using writeBigUInt64LE() method
    buf.writeBigUInt64LE(0xaa03040506efffn, 0);

    // Display the buffer
    console.log(buf);
    ```

    使用以下命令运行 **index.js** 文件:

    ```
    node index.js
    ```

    **输出:**

    ```
    <Buffer ff ef 06 05 04 03 aa 00>

    ```

    **参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/buffer . html # buffer _ buf _ writebiguint64le _ value _ offset](https://nodejs.org/dist/latest-v12.x/docs/api/buffer.html#buffer_buf_writebiguint64le_value_offset)