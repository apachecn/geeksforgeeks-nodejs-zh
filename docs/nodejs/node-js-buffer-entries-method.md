# Node.js Buffer.entries()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-entries-method/](https://www.geeksforgeeks.org/node-js-buffer-entries-method/)

**Buffer.entries()方法**用于从缓冲区的内容创建并返回[索引，字节]对的迭代器。

**语法:**

```
Buffer.entries()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法以[索引，字节]格式返回一个 Iterator 对象对。

下面的例子说明了缓冲区条目()方法在节点中的使用:

**例 1:**

```
// Node program to demonstrate the
// Buffer.entries() method

// Create a Buffer from Buffer.from() function
const buf = Buffer.from('GeeksforGeeks');

for (const pair of buf.entries()) {
    console.log(pair);
}
```

**输出:**

```
[ 0, 71 ]
[ 1, 101 ]
[ 2, 101 ]
[ 3, 107 ]
[ 4, 115 ]
[ 5, 102 ]
[ 6, 111 ]
[ 7, 114 ]
[ 8, 71 ]
[ 9, 101 ]
[ 10, 101 ]
[ 11, 107 ]
[ 12, 115 ]

```

**例 2:**

```
// Node program to demonstrate the
// Buffer.entries() method

// Create a JSON Object
var a = {
    "name": "GeeksforGeeks"
}

// Convert to a string
a = JSON.stringify(a);

// Creating a Buffer
const b = Buffer.from(a);
for( const pair of b.entries())
    process.stdout.write(String.fromCharCode(pair[1]), "");
```

**输出:**

```
{"name":"GeeksforGeeks"}
```

**例 3:**

```
// Node program to demonstrate the
// Buffer.entries() method

// Create an array
var arr = [true, true, false];

// Creating a buffer
const buf = Buffer.from(arr);
for(const pair of buf.entries()) {
    console.log("index " + pair[0] + ", value " + pair[1]);
} 
```

**输出:**

```
index 0, value 1
index 1, value 1
index 2, value 0
```

**参考:**[https://nodejs . org/docs/latest-v 11 . x/API/buffer . html # buffer _ buf _ entries](https://nodejs.org/docs/latest-v11.x/api/buffer.html#buffer_buf_entries)