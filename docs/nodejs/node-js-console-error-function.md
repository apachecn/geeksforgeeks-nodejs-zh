# Node.js console.error()函数

> 原文:[https://www . geesforgeks . org/node-js-console-error-function/](https://www.geeksforgeeks.org/node-js-console-error-function/)

[Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 的控制台类中的**控制台. error()功能**用于在控制台上显示错误信息。它用换行符打印到 stderr。
**语法:**

```js
console.error([data][, ...args])
```

**参数:**该函数可以包含多个参数。第一个参数用于主要消息，其他参数用于替代值。
**返回值:**函数返回错误信息。
以下程序演示控制台的工作。错误()功能:
**程序 1:**

## java 描述语言

```js
// Store number to variable
num = 20

// Check condition
if (num < 100) {
    console.log("Enter number greater then 100");
}
else {
    console.error("correct choice");
}        
```

**输出:**

```js
Enter number greater then 100
```

**程序 2:**

## java 描述语言

```js
// Store number to variable
x = 20;
y = 50;

// Check condition
if (x > y) {
    console.error('%d is greater then %d', x, y);
}
else {
    console.error('%d is less then or equal to %d', x, y);
}
```

**输出:**

```js
20 is less then or equal to 50
```