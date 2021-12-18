# Node.js GM rotate()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-rotate-function/](https://www.geeksforgeeks.org/node-js-gm-rotate-function/)

**旋转()功能**是 GraphicsMagick 库中的内置功能，用于将图像旋转指定的角度。该函数在成功时返回真值。

**语法:**

```js
rotate( angle, color )
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **角度:**该参数存储角度值。
*   **颜色:**此参数将颜色值存储为字符串，该字符串将被设置为背景颜色。

**返回值:**该函数返回添加了图像的 GraphicsMagick 对象。

**原图:**
![](img/3a7f2a0c7a1b7410f45c9428c4fda2ad.png)

**例 1:**

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('gfg.png')

// Invoke rotate function with background
// color as #545651 and rotation angle as
// 78 Degrees clockwise.
.rotate("#545651", 78)

// Process and Write the image
.write("rotate1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/00e6a397b7f1a9f3e022504daa767de0.png)

**例 2:**

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('gfg.png')

// Set stroke color
.stroke("#fe1232")

// Set fill color
.fill("#1200ff")

// Draw Rectangle using drawRectangle function
.drawRectangle(10, 2, 130, 30, 1, 2)

//Invoke Sharpen Function with radius as 10 
.sharpen(10, 4)

// Invoke rotate function with background
// color as #67f123 and rotation angle as
// 45 Degrees clockwise.
.rotate("#67f123", 45)

// Process and Write the image
.write("rotate2.png", function (err) {
    if (!err) console.log('done');
});
```

**输出:**
![](img/989ab2852da496cbafb6785839ec9c00.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html # details-rotate](http://www.graphicsmagick.org/GraphicsMagick.html#details-rotate)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)