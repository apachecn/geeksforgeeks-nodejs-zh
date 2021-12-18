# Node.js GM 漩涡()功能

> 原文:[https://www.geeksforgeeks.org/node-js-gm-swirl-function/](https://www.geeksforgeeks.org/node-js-gm-swirl-function/)

**漩涡()函数**是 GraphicsMagick 库中的一个内置函数，用于图像的中心。度数指定漩涡的紧密度。

**语法:**

```
swirl( angle )
```

**参数:**该功能接受上面提到的和下面描述的单个参数:

*   **角度:**该参数存储涡流的角度。

**返回值:**该函数返回 GraphicsMagick 漩涡图像。

**原图:**
![](img/3a7f2a0c7a1b7410f45c9428c4fda2ad.png)

**例 1:**

```
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke swirl function with
// an angle values as 45
.swirl(45)

// Process and Write the image
.write("swirl1.png", function (err) {
    if (!err) console.log('done');
});
```

**输出:**
![](img/11f1ed7bb114960a3a46dbecc973632e.png)

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

// Invoke swirl function with
// an angle value as -270 
.swirl(-270)

// Process and Write the image
.write("swirl2.png", function (err) {
    if (!err) console.log('done');
});
```

**输出:**
![](img/8143134cb50a1a9b20e7972833a5cd18.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html #详情-漩涡](http://www.graphicsmagick.org/GraphicsMagick.html#details-swirl)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)