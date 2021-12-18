# 节点 js GM 锐化()功能

> 原文:[https://www.geeksforgeeks.org/node-js-gm-sharpen-function/](https://www.geeksforgeeks.org/node-js-gm-sharpen-function/)

**锐化()函数**是 GraphicsMagick 库中的一个内置函数，用于锐化图像。它使用给定半径和标准偏差(σ)的高斯算子。

**语法:**

```
sharpen( radius, sd )
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **半径:**该参数存储锐度的半径值。
*   **sd:** 是存储图像标准差的可选参数。

**返回值:**该函数返回 Gmagick 锐化图像。

**原图:**
![](img/3a7f2a0c7a1b7410f45c9428c4fda2ad.png)

**例 1:**

```
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke sharpen function with
// radius as 10 ad standard
// deviation as 2
.sharpen(10, 2)

// Process and Write the image
.write("1b.png", function (err) {
    if (!err) console.log('done');
});
```

**输出:**
![](img/0e8533d54f8411cd6eb2fffa89e18cde.png)

**例 2:**

```
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Set stroke color
.stroke("#fe1232")

// Set fill color
.fill("#1200ff")

// Draw Rectangle using drawRectangle function
.drawRectangle(10, 2, 130, 30, 1, 2)

// Invoke Sharpen Function with radius as 10 
.sharpen(10)

// Process and Write the image
.write("1a.png", function (err) {
    if (!err) console.log('done');
});
```

**输出:**
![](img/22a44effa0c3a420e0dcf30e76860990.png)

**参考:**

*   [http://www.graphicsmagick.org/GraphicsMagick.html#sharpen](http://www.graphicsmagick.org/GraphicsMagick.html#sharpen)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)