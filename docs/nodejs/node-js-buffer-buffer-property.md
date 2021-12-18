# 节点. js 缓冲区.缓冲区属性

> 原文:[https://www . geesforgeks . org/node-js-buffer-buffer-property/](https://www.geeksforgeeks.org/node-js-buffer-buffer-property/)

**Buffer.buffer** 属性是缓冲模块中类 **Buffer** 的内置应用编程接口，用于获取数组缓冲区中与该缓冲区对象等效的对象。

**语法:**

```js
const buf.buffer
```

**返回值:**该属性返回数组缓冲区的对象。

**示例 1:** **文件名:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// Buffer.buffer property

// Creating a Buffer
const buff = Buffer.from([1, 2, 3, 4, 5]);

// Getting the value of array buffer
const value = buff.buffer;

// Display the result
console.log("Big Integer :- " + value);
```