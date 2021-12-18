# node . js V8 . getheapstatics()方法

> 原文:[https://www . geesforgeks . org/node-js-V8-getheap statistics-method/](https://www.geeksforgeeks.org/node-js-v8-getheapstatistics-method/)

**v8 . getheapstaticts()方法**是 v8 模块的内置应用编程接口，用于获取从 V8 版本派生的堆的统计信息。

**语法:**

```js
v8.getHeapStatistics();
```

**参数:**该方法没有任何参数。

**返回值:**这个方法返回一个包含版本 8 堆统计信息的对象。返回的对象通常包含一个数组，该数组由以下字段组成:

*   **Total _ heap _ size** : A number indicating the total heap size.
*   **Total _ heap _ size _ executive** : A number indicating the total size of the executable heap.
*   [T0】 total _ physical _ size 【T1]: A number representing the total physical size.
*   [T0】 total _ available _ size 【T1]: A number indicating the total available size.
*   [T0】 used _ heap _ size 【T1]: a number indicating the used heap size.
*   **heap size limit** : a number indicating the heap size limit.
*   **玛洛蒂 _ memory** :云娥，什么事记忆模糊。
*   **peak _ malloced _ memory** :一个数字,表示最大记忆记忆.
*   [T0】 do _ zap _ garbage dump : A number, especially a Boolean value, indicating whether the–-zap _ code _ space option is enabled or not.
*   **number _ of _ native _ contexts** : a number indicating the number of native contexts or top-level contexts currently active. Memory leakage can be indicated by measuring the increment of this number with time.
*   **Number _ of _ disconnected _ contexts** : A number that represents multiple separated contexts or contexts that have been separated but not yet garbage collected. If it has a non-zero value, it may indicate a memory leak.

下面的例子说明了在 Node.js 中使用 v8.getHeapStatistics()方法

**示例 1:** **文件名:index.js**

```js
// Accessing v8 module
const v8 = require('v8');

// Calling v8.getHeapStatistics() 
console.log(v8.getHeapStatistics());
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
{ total_heap_size: 6537216,
  total_heap_size_executable: 1048576,
  total_physical_size: 6537216,
  total_available_size: 1520717240,
  used_heap_size: 4199600,
  heap_size_limit: 1526909922,
  malloced_memory: 8192,
  peak_malloced_memory: 406408,
  does_zap_garbage: 0 }

```

**示例 2:** **文件名:**

```js
// Accessing v8 module
const v8 = require('v8');

// Calling v8.getHeapStatistics() 
stats = v8.getHeapStatistics();
console.log("Heap Stastistics are :");

console.log("total_heap_size:"+stats['total_heap_size']);
console.log("used_heap_size:"+stats['used_heap_size']);
console.log("heap_size_limit:"+stats['heap_size_limit']);
console.log("does_zap_garbage:"+stats['does_zap_garbage']);
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Heap Stastistics are :
total_heap_size:6537216
used_heap_size:4200640
heap_size_limit:1526909922
does_zap_garbage:0

```

**参考:**T2】https://nodejs.org/api/v8.html#v8_v8_getheapstatistics