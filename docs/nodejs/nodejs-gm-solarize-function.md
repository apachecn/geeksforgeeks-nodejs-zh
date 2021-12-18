# Nodejs | GM solarize()功能

> 原文:[https://www.geeksforgeeks.org/nodejs-gm-solarize-function/](https://www.geeksforgeeks.org/nodejs-gm-solarize-function/)

**solarize()** 函数是 GraphicsMagick 库中的一个内置函数，用于否定阈值以上的所有像素。该函数在成功时返回真值。
**语法:**

```js
solarize(thresholdLevel)
```

**参数:**该功能接受单个参数**阈值水平**，用于指定 0 到 100 之间的阈值水平。
**返回值:**该函数返回 GraphicsMagick 对象。
**例 1:**

## java 描述语言

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke solarize function
.solarize(12)

// Process and Write the image
.write("solarize1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**

![](img/c0bfd85b30c10ec1ebcf4567e91823b7.png)

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

//Call to drawText Function
.drawText(100, 280, "GeeksforGeeks!")

// Invoke borderColor() function
// and set border color to green
.borderColor("Green")

// Invoke border function
.border(62, 32)

// Invoke solarize function
.solarize(3)

// Process and Write the image
.write("solarize2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**

![](img/7eae2439d45a8cb45d6a27d2f0475dd9.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html # details-solarize](http://www.graphicsmagick.org/GraphicsMagick.html#details-solarize)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)