# Node.js GM 行程()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-stroke-function/](https://www.geeksforgeeks.org/node-js-gm-stroke-function/)

**描边()函数**是 GraphicsMagick 库中的一个内置函数，用于设置用于绘制对象轮廓的描边的颜色和宽度。

**语法:**

```
stroke( color, width )
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **颜色:**该参数存储笔画的颜色。
*   **宽度:**这是存储对象宽度的可选参数。

**返回值:**该函数返回添加了图像的 GraphicsMagick 对象。

**原图:**
![](img/3a7f2a0c7a1b7410f45c9428c4fda2ad.png)

**例 1:**

```
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Set stroke color and size
.stroke("#fe1232", 5)

// Set fill color
.fill("#56f864")

// Draw Circle using drawCircle function
.drawCircle(120, 50, 100, 60).stroke()

// Process and Write the image
.write("1a.png", function (err) {
    if (!err) console.log('done');
});
```

**输出:**
![](img/a35ad963ecaca51d209d7368c7fb5f2a.png)

**例二:**
**原图:**
![](img/3a7f2a0c7a1b7410f45c9428c4fda2ad.png)
**程序:**

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

// Process and Write the image
.write("1a.png", function (err) {
    if (!err) console.log('done');
});
```

**输出:**
![](img/dea129c6f7620dc5044bec76a6387be8.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html # details-stroke](http://www.graphicsmagick.org/GraphicsMagick.html#details-stroke)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)