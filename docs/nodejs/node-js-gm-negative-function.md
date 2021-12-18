# Node.js GM 负()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-negative-function/](https://www.geeksforgeeks.org/node-js-gm-negative-function/)

**negative()** 函数是 GraphicsMagick 库中的一个内置函数，用于将每个像素替换为其补色。该函数在成功时返回真值。
**语法:**

```js
negative()
```

**参数:**此功能不接受任何参数。
**返回值:**该函数返回 GraphicsMagick 对象。
**例 1:**

## java 描述语言

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke Negative function
.negative()

// Process and Write the image
.write("negative1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**

![](img/274b607cad3a5d05b0c3a6d6fbfd372b.png)

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

// Invoke negative function
.negative()

// Process and write the image 
.write("negative2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**

![](img/8d7e302f79c30ed6da4247fb0aae5973.png)

**例 3:**

## java 描述语言

```js
// Include gm library
var gm = require('gm');
gm('1.png')

// Include another image
.composite('operator-noise-multiplicative1.png')

// Shift the image using geometry function
.geometry('+10+50')

// Invoke compose function with 'plus' Argument
.compose('plus')

// Include another image
.composite('randomThreshold1.png')

// Shift the image using geometry function
.geometry('+20+70')

// Invoke compose function with 'plus' argument
.compose('plus')

// Invoke negative function
.negative()

// Process and write the image
.write('negative3.png', function(err) {
    if(!err) console.log("Written composite image.");
});
```

**输出:**

![](img/ade72ef545a97ff22efe1f9012361d64.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html #详情-否定](http://www.graphicsmagick.org/GraphicsMagick.html#details-negate)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)