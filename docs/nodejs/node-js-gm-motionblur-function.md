# Node.js GM motionBlur()函数

> 原文:[https://www . geesforgeks . org/node-js-GM-motion blur-function/](https://www.geeksforgeeks.org/node-js-gm-motionblur-function/)

**运动模糊()函数**是 GraphicsMagick 库中的一个内置函数，用于使用具有可配置半径、σ和角度的高斯卷积核来应用运动模糊效果。该函数返回成功的真实值。

**语法:**

```
motionBlur(radius, sigma, angle)
```

**参数:**该功能接受上面提到的和下面描述的三个参数:

*   **半径:**此参数用于指定半径的值。
*   **西格玛:**该参数用于指定西格玛的值。
*   **角度:**此参数用于指定角度的弧度值。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

## java 描述语言

```
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke borderColor() function
// and set border color to green
.borderColor('Green')

// Invoke resize function
.border(10,30)

// Invoke motionblur function
.motionBlur(10,30,30)

// Process and Write the image
.write("motionblur1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**

![](img/c2022e0bd7ec359ba791f348ece7adfe.png)

**例 2:**

## java 描述语言

```
// Include gm library
var gm = require('gm');

// Import the image
gm(600,300,'white')

// Set the color for the stroke
.stroke("green",3)

// Set the font 
.font("Helvetica.ttf",60)

// Call to drawText Function
.drawText(100, 280, "GeeksforGeeks!")

// Invoke borderColor() function
// and set border color to green
.borderColor("Green")

// Invoke border function
.border(62,32)

// Invoke motionBlur() function
.motionBlur(10,10,10)

// Process and write the image 
.write("motionblur2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**

![](img/cba99d9099a5103d797fb8a9b48b6c55.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html # details-motion-blur](http://www.graphicsmagick.org/GraphicsMagick.html#details-motion-blur)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)