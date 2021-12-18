# Node.js GM 对比度()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-contrast-function/](https://www.geeksforgeeks.org/node-js-gm-contrast-function/)

**对比度()**功能是 GraphicsMagick 库中的一个内置功能，用于增强或降低图像的对比度。该函数在成功时返回真值。
**语法:**

```js
contrast(multiplier)
```

**参数:**该功能接受单个参数**乘数**，即图像对比度应增加或减少的因子。
**返回值:**该函数返回 GraphicsMagick 对象。
**例 1:**

## java 描述语言

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke contrast function
.contrast(10)

// Process and Write the image
.write("contrast1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**

![](img/d47aff458780ecb109c834af5a550a1f.png)

**例 2:**

## java 描述语言

```js
// Include gm library
var gm = require('gm');

// Import the image
gm(600, 300, 'white')

// Set the color for the stroke
.stroke("green", 3)

// Set the font 
.font("Helvetica.ttf", 60)

// Call to drawText Function
.drawText(100, 280, "GeeksforGeeks!")

// Invoke borderColor() function
// and set border color to green
.borderColor("Green")

// Invoke border function
.border(62, 32)

// Invoke contrast function
.contrast(-14)

// Process and Write the image
.write("contrast2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**

![](img/e57e4cd17f3713d8ca2d2c254bfa501d.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html #详情-对比](http://www.graphicsmagick.org/GraphicsMagick.html#details-contrast)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)